<script setup lang="ts">
import { reactive } from "vue";
const controls = reactive({
  throttle: 0,
  roll: 0,
  pitch: 0,
});

const isConnected = ref(false);

interface ControlsInput {
  roll: number;
  throttle: number;
  pitch: number;
}

function submitInputs() {
  const controlsInput: ControlsInput = {
    throttle: controls.throttle,
    roll: controls.roll,
    pitch: controls.pitch,
  };
  connection.send(JSON.stringify(controlsInput));
}

const connection = new WebSocket("ws://20.123.77.40:3000");

connection.onopen = function (event) {
  isConnected.value = true;
  setInterval(() => submitInputs(), 100);
};
connection.onclose = function (event) {
  isConnected.value = false;
};

const map = new Map();
map.set("ArrowUp", "i-heroicons-plus");
map.set("ArrowDown", "i-heroicons-minus");
map.set("ArrowRight", "i-heroicons-arrow-small-right");
map.set("ArrowLeft", "i-heroicons-arrow-small-left");
map.set("8", "i-heroicons-arrow-up");
map.set("2", "i-heroicons-arrow-down");

function validCommand(
  currentValue: number,
  step: number,
  limit: number,
  operator: string
): boolean {
  if (operator == "<=") {
    return currentValue + step <= limit;
  }
  if (operator == ">=") {
    return currentValue + step >= limit;
  }
  if (operator == ">") {
    return currentValue + step > limit;
  }
  if (operator == "<") {
    return currentValue + step < limit;
  } else {
    return false;
  }
}

const keyPressed = ref("");

window.addEventListener("keydown", (e) => {
  keyPressed.value = e.key;
  console.log(keyPressed.value);
  if (e.key == "W" || e.key == "w") {
    if (validCommand(controls.throttle, 0.1, 1, "<=")) {
      controls.throttle += 0.1;
    }
  }
  if (e.key == "s" || e.key == "S") {
    if (validCommand(controls.throttle, -0.1, 0, ">")) {
      controls.throttle -= 0.1;
    }
  }
  if (e.key == "ArrowRight") {
    if (validCommand(controls.roll, 0.1, 1, "<=")) {
      controls.roll += 0.1;
    }
  }
  if (e.key == "ArrowLeft") {
    if (validCommand(controls.roll, -0.1, -1, ">=")) {
      controls.roll -= 0.1;
    }
  }
  if (e.key == "ArrowUp") {
    if (validCommand(controls.pitch, 0.1, 1, "<=")) {
      controls.pitch += 0.1;
    }
  }
  if (e.key == "ArrowDown") {
    if (validCommand(controls.pitch, -0.1, -1, ">=")) {
      controls.pitch -= 0.1;
    }
  }
});
</script>
<template>
  <div
    class="h-screen w-[400px] bg-white flex items-center gap-8 p-2 flex-col justify-center"
  >
    <UBadge
      size="lg"
      variant="outline"
      :color="isConnected ? 'green' : 'red'"
      :label="isConnected ? 'Conectado' : 'Desconectado'"
    ></UBadge>
    <div class="bg-gray-200 p-4 shadow-lg rounded-lg flex flex-col gap-2">
      <p class="text-black text-center font-bold">Controles</p>

      <div class="text-black flex gap-2">
        <UKbd>W</UKbd>
        <p>: Aumentar throttle</p>
      </div>
      <div class="text-black flex gap-2">
        <UKbd>S</UKbd>
        <p>: Disminuir throttle</p>
      </div>
      <div class="text-black flex gap-2">
        <UKbd>←</UKbd>
        <p>: Roll hacia la izquierda</p>
      </div>
      <div class="text-black flex gap-2">
        <UKbd>→</UKbd>
        <p>: Roll hacia la derecha</p>
      </div>
      <div class="text-black flex gap-2">
        <UKbd>↑</UKbd>
        <p>: Pitch hacia arriba</p>
      </div>
      <div class="text-black flex gap-2">
        <UKbd>↓</UKbd>
        <p>: Pitch hacia abajo</p>
      </div>
    </div>

    <UButton :icon="map.get(keyPressed)">{{ keyPressed }}</UButton>

    <p class="text-black text-center">Throttle</p>
    <UProgress :value="controls.throttle * 100" indicator></UProgress>

    <p class="text-black">Roll: {{ controls.roll.toFixed(3) }}</p>
    <p class="text-black">Pitch: {{ controls.pitch.toFixed(3) }}</p>

    <div
      class="w-[300px] h-[300px] bg-center bg-no-repeat bg-contain"
      :class="['bg-[url(/joystick.png)]']"
    >
      <div
        :style="{ top: `${125 - controls.throttle * 10}px` }"
        class="w-[50px] h-[50px] bg-blue-500 rounded-full relative left-[78px]"
      ></div>
      <div
        :style="{
          top: `${76 - controls.pitch * 10}px`,
          left: `${174 + controls.roll * 10}px`,
        }"
        class="w-[50px] h-[50px] bg-red-500 rounded-full relative"
      ></div>
    </div>
  </div>
</template>

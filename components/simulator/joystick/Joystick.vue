<script setup lang="ts">
import { computed } from "vue";
const throttle = ref(0);
const roll = ref(0);
const pitch = ref(0);
const yaw = ref(0);

const getFirstAxis = computed(() => {
  const base = 123;
  return "top-[" + (base + throttle.value * 10).toString() + "px]";
});

interface ControlsInput {
  roll: number;
  throttle: number;
  pitch: number;
}

function submitInputs() {
  const controlsInput: ControlsInput = {
    throttle: throttle.value,
    roll: roll.value,
    pitch: pitch.value,
  };

  console.log("enviamos dato");
  connection.send(JSON.stringify(controlsInput));
}
const connection = new WebSocket("ws://20.123.77.40:3000");

connection.onopen = function (event) {
  setInterval(() => submitInputs(), 400);
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
  if (e.key == "ArrowUp") {
    if (validCommand(throttle.value, 0.1, 1, "<=")) {
      throttle.value += 0.1;
    }
  }
  if (e.key == "ArrowDown") {
    if (validCommand(throttle.value, -0.1, 0, ">")) {
      throttle.value -= 0.1;
    }
  }
  if (e.key == "ArrowRight") {
    if (validCommand(roll.value, 0.1, 1, "<=")) {
      roll.value += 0.1;
    }
  }
  if (e.key == "ArrowLeft") {
    if (validCommand(roll.value, -0.1, -1, ">=")) {
      roll.value -= 0.1;
    }
  }
  if (e.key == "8") {
    if (validCommand(pitch.value, 0.1, 1, "<=")) {
      pitch.value += 0.1;
    }
  }
  if (e.key == "2") {
    if (validCommand(pitch.value, -0.1, -1, ">=")) {
      pitch.value -= 0.1;
    }
  }
});
</script>
<template>
  <div
    class="h-screen w-[400px] bg-white flex items-center gap-8 p-2 flex-col justify-center"
  >
    <div class="bg-gray-200 p-4 shadow-lg rounded-lg">
      <p class="text-black text-center">Controles</p>
      <div class="text-black flex gap-2">
        <UKbd>↑</UKbd>
        <p>: Aumentar throttle</p>
      </div>
      <div class="text-black flex gap-2">
        <UKbd>↓</UKbd>
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
        <UKbd>8</UKbd>
        <p>: Pitch hacia arriba</p>
      </div>
      <div class="text-black flex gap-2">
        <UKbd>2</UKbd>
        <p>: Pitch hacia abajo</p>
      </div>
    </div>
    <div
      class="flex flex-col justify-center items-center bg-gray-200 p-4 shadow-xl rounded-lg"
    >
      <UButton :icon="map.get(keyPressed)"></UButton>
      <div>
        <p class="text-black text-center">Throttle</p>
        <UProgress :value="throttle * 100" indicator></UProgress>
      </div>
      <p class="text-black">Roll: {{ roll.toFixed(3) }}</p>
      <p class="text-black">Pitch: {{ pitch.toFixed(3) }}</p>
    </div>
    <div
      class="w-[300px] h-[300px] bg-center bg-no-repeat bg-contain"
      :class="['bg-[url(/joystick.png)]']"
    >
      <div
        :style="{ top: `${125 - throttle * 10}px` }"
        class="w-[50px] h-[50px] bg-blue-500 rounded-full relative left-[78px]"
      ></div>
      <div
        :style="{ top: `${76 - pitch * 10}px`, left: `${174 + roll * 10}px` }"
        class="w-[50px] h-[50px] bg-red-500 rounded-full relative"
      ></div>
    </div>
  </div>
</template>

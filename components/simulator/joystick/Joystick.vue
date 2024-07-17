<script setup lang="ts">
const throttle = ref(0);
const roll = ref(0);
const pitch = ref(0);
const yaw = ref(0);

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

const keyPressed = ref("");

window.addEventListener("keydown", (e) => {
  keyPressed.value = e.key;
  if (e.key == "ArrowUp") {
    throttle.value += 0.1;
  }
  if (e.key == "ArrowDown") {
    throttle.value -= 0.1;
  }
  if (e.key == "ArrowRight") {
    roll.value += 0.1;
  }
  if (e.key == "ArrowLeft") {
    roll.value -= 0.1;
  }
  if (e.key == "8") {
    pitch.value += 0.1;
  }
  if (e.key == "2") {
    pitch.value -= 0.1;
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
  </div>
</template>

<script setup lang="ts">
import { reactive, ref, onMounted, onUnmounted } from "vue";

// Configuración de controles
const controls = reactive({
  throttle: 0.6,
  roll: 0,
  pitch: 0,
});

// Estado de conexión WebSocket
const isConnected = ref(false);

// Interfaz para los datos de control
interface ControlsInput {
  roll: number;
  throttle: number;
  pitch: number;
}

// Función para enviar los datos de control
function submitInputs() {
  const controlsInput: ControlsInput = {
    throttle: controls.throttle,
    roll: controls.roll,
    pitch: controls.pitch,
  };
  console.log("Sending controls:", controlsInput); // Ver valores antes de enviar
  connection.send(JSON.stringify(controlsInput));
}

// Conexión WebSocket
const connection = new WebSocket("wss://simulation.dae.com.co/socket");

connection.onopen = function () {
  isConnected.value = true;
  setInterval(() => submitInputs(), 100);
};

connection.onclose = function () {
  isConnected.value = false;
};

connection.onerror = function (error) {
  console.error("WebSocket Error: ", error);
};

connection.onmessage = function (event) {
  const data = JSON.parse(event.data);
  // Procesar datos recibidos del WebSocket
};

// Lógica para el uso del Gamepad
let gamepadIndex = -1;

function connectGamepad(event: GamepadEvent) {
  gamepadIndex = event.gamepad.index;
  console.log("Gamepad connected at index:", gamepadIndex, "ID:", event.gamepad.id);
}

function disconnectGamepad(event: GamepadEvent) {
  console.log("Gamepad disconnected from index:", event.gamepad.index);
  gamepadIndex = -1;
}

function updateGamepad() {
  console.log("updateGamepad called"); // Verifica si esta línea se ejecuta
  if (gamepadIndex === -1) return;

  const gamepad = navigator.getGamepads()[gamepadIndex];
  if (!gamepad) {
    console.log("No gamepad found at index:", gamepadIndex);
    return;
  }

  // Imprime todos los ejes y botones para ver sus valores
  console.log("Gamepad axes:", gamepad.axes);
  console.log("Gamepad buttons:", gamepad.buttons);

  // Escalado de los ejes del Gamepad usando índices
  const roll = gamepad.axes[0]; // Eje X del stick izquierdo
  const pitch = gamepad.axes[1]; // Eje Y del stick izquierdo
  const throttle = (gamepad.axes[3] + 1) / 2; // Eje X del stick derecho

  // Actualización de los controles
  controls.roll = roll;
  controls.pitch = pitch;
  controls.throttle = throttle;

  // Mostrar los valores actuales de los controles en la consola
  console.log("Controls:", {
    roll: controls.roll.toFixed(3),
    pitch: controls.pitch.toFixed(3),
    throttle: controls.throttle.toFixed(3),
  });

  requestAnimationFrame(updateGamepad);
}

onMounted(() => {
  window.addEventListener("gamepadconnected", connectGamepad);
  window.addEventListener("gamepaddisconnected", disconnectGamepad);
  requestAnimationFrame(updateGamepad);
});

onUnmounted(() => {
  window.removeEventListener("gamepadconnected", connectGamepad);
  window.removeEventListener("gamepaddisconnected", disconnectGamepad);
});
</script>

<template>
  <div class="h-screen w-[400px] bg-white flex items-center gap-8 p-2 flex-col justify-center">
    <UBadge size="lg" variant="outline" :color="isConnected ? 'green' : 'red'" :label="isConnected ? 'Conectado' : 'Desconectado'"></UBadge>
    <div class="bg-gray-200 p-4 shadow-lg rounded-lg flex flex-col gap-2">
      <p class="text-black text-center font-bold">Controles</p>
    </div>
    <p class="text-black text-center">Throttle</p>
    <UProgress :value="controls.throttle * 100" indicator></UProgress>
    <p class="text-black">Roll: {{ controls.roll.toFixed(3) }}</p>
    <p class="text-black">Pitch: {{ controls.pitch.toFixed(3) }}</p>
    <div class="w-[300px] h-[300px] bg-center bg-no-repeat bg-contain" :class="['bg-[url(/joystick.png)]']">
      <div :style="{ top: ${125 - controls.throttle * 10}px }" class="w-[50px] h-[50px] bg-blue-500 rounded-full relative left-[78px]"></div>
      <div :style="{ top: ${76 - controls.pitch * 10}px, left: ${174 + controls.roll * 10}px }" class="w-[50px] h-[50px] bg-red-500 rounded-full relative"></div>
    </div>
  </div>
</template>

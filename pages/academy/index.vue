<template>
  <NuxtLayout>
    <div class="w-screen flex">
      <div class="buttons-container flex gap-4 w-[90%] mt-[20px] mx-auto">
        <UButton
          @click="changeMode('administrador')"
          size="xl"
          class=""
          color="gray"
          >Administrator</UButton
        >
        <UButton @click="console.log('???')" size="xl" color="gray"
          >Instructor</UButton
        >
        <p class="text-black">{{ mode }}</p>

        <div v-if="mode">
          <p>eres administrador</p>
          <ul>
            <li>inscribir</li>
            <li>borrar</li>
          </ul>
        </div>
      </div>
    </div>
  </NuxtLayout>
</template>

<script setup>
import { ref } from "vue";

const mode = ref("");

function changeMode(desiredMode) {
  mode.value = desiredMode;
  console.log(mode);
}
</script>

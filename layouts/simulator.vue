<template>
  <main class="flex h-screen bg-red-40 w-screen">
    <SimulatorSider></SimulatorSider>
    <slot>
      <iframe class="w-full" src="https://api.memorise.com.co:8080"></iframe>
    </slot>
  </main>
</template>

<template>
  <main class="flex h-screen bg-red-40 w-screen">
    <SimulatorSider></SimulatorSider>
    <slot>
      <iframe src="https://api.memorise.com.co"></iframe>
    </slot>
  </main>
</template>

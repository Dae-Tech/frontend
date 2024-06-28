<template>
  <main class="flex h-screen bg-red-40 w-screen">
    <SimulatorSider></SimulatorSider>
    <slot>
      <iframe src="http://40.113.49.19:8080/"></iframe>
    </slot>
  </main>
</template>

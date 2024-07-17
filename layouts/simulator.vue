<template>
  <main class="flex h-screen bg-red-40 w-screen">
    <SimulatorSider></SimulatorSider>
    <slot>
      <SimulatorJoystick></SimulatorJoystick>
      <iframe class="w-full" src="http://20.123.77.40:8080"></iframe>
    </slot>
  </main>
</template>

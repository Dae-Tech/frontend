<template>
  <main class="flex h-screen bg-red-40 w-screen">
    <SimulatorSider></SimulatorSider>
    <slot>
      <SimulatorJoystick></SimulatorJoystick>
      <iframe class="w-full" src="https://simulation.dae.com.co/"></iframe>
    </slot>
  </main>
</template>

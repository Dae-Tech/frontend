<template>
    <NuxtLayout>
        <template #firstSpace>
            <NuxtLink class="boxHome" to="/"><button>Log Out</button></NuxtLink>
            <div class="user">Pilot Name</div>
            <div class="sub">My subscription</div>
        </template>
        <div class="accessSim">ENTER SIMULATOR</div>
        <NuxtImg
                src="/New_Logo-01.jpg"
                sizes="100vw sm:30vw"
        />
        <div style="color: #4BA9C7; width: 30vw; font-size: 3vw; text-align: center;">DRONE SIMULATOR</div>
    </NuxtLayout>
  </template>
  
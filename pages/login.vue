<template>
  <NuxtLayout>
    <template #firstSpace>
      <NuxtLink class="boxHome" to="/"><button>Home Page</button></NuxtLink>
    </template>
    <div style="padding: 1vw; float: left;">
      <NuxtImg
        src="/New_Logo-01.jpg"
        sizes="100vw sm:30vw"
      />
      <div style="color: #4BA9C7; width: 30vw; font-size: 3vw; text-align: center;">DRONE SIMULATOR</div>
    </div>
    <div class="Log">
      <div class="logForm">E-mail</div>
      <input class="inputLog" type="email" placeholder="Type here">
      <div class="logForm">Password</div>
      <input class="inputLog" type="password" placeholder="Type here"><br>
      <NuxtLink to="/academy/home_academy">
        <input type="submit" value="Log in" class="boxLogin">
      </NuxtLink>
    </div>
  </NuxtLayout>
</template>
<template>
  <NuxtLayout>
    <template #firstSpace>
      <div class="tittleSecondSpace">Register new account</div>
      <NuxtLink class="boxHome" to="/"><button>Home Page</button></NuxtLink>
    </template>
    <div class="selectAccount">Select the type of account you would like to register:</div>
    <NuxtLink class="academyAccount" to="/register_academy"><button>I would like to register as an <div style="font-weight: bold;">Academy</div></button></NuxtLink>
    <NuxtLink class="individualAccount" to="/register_individual"><button>I would like to register as an <div style="font-weight: bold;">Individual</div></button></NuxtLink>
  </NuxtLayout>
</template>

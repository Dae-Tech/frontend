<template>
    <NuxtLayout>
        <template #firstSpace>
            <h1 class="tittleSecondSpace">Register new individual account</h1>
            <NuxtLink class="boxHome" to="/"><button>Home Page</button></NuxtLink>
        </template>
        <section class="principalSpace">
            <div class="individualForm">Full name (first name and last name)</div>
            <input class="inputRegister" type="text" placeholder="Type here">
            <div class="individualForm">E-mail</div>
            <input class="inputRegister" type="email" placeholder="Type here">
            <div class="individualForm">Password</div>
            <input class="inputRegister" type="password" placeholder="Type here">
            <div class="individualForm">Confirm Password</div>
            <input class="inputRegister" type="password" placeholder="Type here">
            <div class="managementPolicy">I agree with information management policy <input type="checkbox"></div>
            <input type="submit" value="Register" class="registerBox">
        </section>
    </NuxtLayout>
  </template>
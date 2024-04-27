<template>

    <link rel="stylesheet" href="/after/css/bootstrap.min.css">
    <link rel="stylesheet" href="/after/css/styles.css">
    <!-- horizontal -->
    <section class="firstSpace">
            <NuxtLink class="boxRegister" to="/registration"><button>Register</button></NuxtLink>
            <NuxtLink class="boxLogin" to="/login"><button>Log in</button></NuxtLink>
    </section>
    <section class="principalSpace">
        <slot />
    </section>


    


</template>

<script>
import '~/assets/css/style.css'
</script>

<style>
@import url("~/assets/css/style.css");
</style>
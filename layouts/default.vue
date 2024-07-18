<template>


    <!-- horizontal -->
    <section class="firstSpace">
        <slot name="firstSpace" />
    </section>
    <section class="principalSpace">
        <slot />
    </section>

</template>

<style scoped>
    .firstSpace {
        box-sizing: content-box;
        height: 20vh;
        background-color: #2D4C9A;

    }
    .principalSpace {
        box-sizing: content-box;
        height: 80vh;
        background-color: white;
    }
</style>
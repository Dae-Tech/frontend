<template>
    
        <UCard>
    <template #header>
        {{ title }}
      <Placeholder class="h-8" />
    </template>
    
    <p>Contenido</p>
    <Placeholder class="h-32" />

    <template #footer>
        {{ teacher }}
      <Placeholder class="h-8" />
    </template>
  </UCard>

 
</template>

<script setup>
defineProps({
    title: String,
    teacher: String

})

</script>

<style scoped>
div{
    background-color: red;
}

</style>
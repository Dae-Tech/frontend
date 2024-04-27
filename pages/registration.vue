<template>
    <div>
        <Curso title="Aerodinámica" teacher="Alvarado"></Curso>
        <Curso title="Agricultura" teacher="Juanito"></Curso>
        <Curso title="Control" teacher="Benigno"></Curso>
        <UPopover>
        <UButton color="white" label="Open" trailing-icon="i-heroicons-chevron-down-20-solid" />

        <template #panel>
        <div class="p-4">
            <Placeholder class="h-20 w-48" />
      </div>
    </template>
  </UPopover>
        
    </div>
</template>
<script setup>
    import {ref} from 'vue'
    // api -> devuelve algo
    const libros = ref(["aerodinamica","calculo"])
</script>
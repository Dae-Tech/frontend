<template>
    <NuxtLayout>
        <template #firstSpace>
            <NuxtLink class="boxHome" to="/"><button>Log Out</button></NuxtLink>
        </template>
        <div style="padding: 1vw; float: right;">
            <div style="position: absolute; top: 30px; left: 50px; color: white; font-size: 1.5em;">Drone School</div>

            <div style="position: absolute; top: 20px; left: 270px;">
                <NuxtImg src="/user_image.png" alt="Imagen" style="width: 75px; height: auto;" />
            </div>

            <div style="position: absolute; top: 40px; left: 350px; color: white; font-size: 1em;">Admin. 1</div>
            <div style="position: absolute; top: 160px; left: 70px;">
                <NuxtLink style="text-decoration: none;">
                    <button style="color: black; background-color: white; border: 2px solid black; border-radius: 10px; padding: 5px 10px; margin-right: 10px;">Administrator</button>
                </NuxtLink>
                <button style="color: black; background-color: white; border: 2px solid #4BA9C7; border-radius: 10px; padding: 5px 10px;">Instructor</button>
            </div>
           <div style="position: absolute; top: 200px; left: 70px;">
                <NuxtLink to="/academy/home_academy" style="text-decoration: none;">
                    <button style="color: black; padding: 3px 8px; margin-right: 10px; font-size: 0.8em;">Back</button>
                </NuxtLink>
            </div>

            <!-- Contenedor del primer botón -->
            <div style="position: absolute; top: 240px; left: 70px;">
                <div class="bullet-button">
                <NuxtLink to="/academy/home_academy_instructor_ass_available_1" style="text-decoration: none;">
                    <button style="color: black; padding: 5px 10px; margin-bottom: 10px;"><strong>Basic movements</strong></button>
                </NuxtLink>
                </div>
            </div>
            <!-- Contenedor del segundo botón -->
            <div style="position: absolute; top: 340px; left: 70px;">
                <div class="bullet-button">
                 <NuxtLink to="/academy/home_academy_instructor_ass_available_2" style="text-decoration: none;">
                    <button style="color: black; padding: 5px 10px;"><strong>Position Control</strong></button>
                </NuxtLink>
                </div>
            </div>
            <NuxtImg
                src="/New_Logo-01.jpg"
                sizes="50vw sm:20vw" 
            />
            <div style="color: #4BA9C7; width: 15vw; font-size: 1vw; text-align: right;">DRONE SIMULATOR</div>
            <NuxtLink class="boxHome"><button>Enter Simulation</button></NuxtLink>
        </div>
    </NuxtLayout>
</template>

<style>
.bullet-button {
  display: flex;
  align-items: center;
}

.bullet-button::before {
  content: "\2022"; /* Código Unicode para el carácter de viñeta */
  color: black; /* Color de la viñeta */
  font-size: 1.5em; /* Tamaño de la viñeta */
  margin-right: 10px; /* Espacio entre la viñeta y el botón */
}
</style>
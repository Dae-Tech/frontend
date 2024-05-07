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
                <NuxtLink to="/academy/home_academy_admin" style="text-decoration: none;">
                    <button style="color: black; background-color: white; border: 2px solid black; border-radius: 10px; padding: 5px 10px; margin-right: 10px;">Administrator</button>
                </NuxtLink>
                <button style="color: black; background-color: white; border: 2px solid black; border-radius: 10px; padding: 5px 10px;">Instructor</button>
            </div>
            <NuxtImg
                src="/New_Logo-01.jpg"
                sizes="50vw sm:20vw" 
            />
            <div style="color: #4BA9C7; width: 15vw; font-size: 1vw; text-align: right;">DRONE SIMULATOR</div>
            <NuxtLink><button>Enter Simulation</button></NuxtLink>
            <div style="position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%); color: black; font-size: 1em; text-align: center;">Please select a role...</div>
        </div>
    </NuxtLayout>
</template>
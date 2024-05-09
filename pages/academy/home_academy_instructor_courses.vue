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
            <div style="position: absolute; top: 240px; left: 70px;">
                <!-- Cuatro botones adicionales -->
                <NuxtLink to="/academy/home_academy_instructor" style="text-decoration: none;">
                    <button style="color: black; padding: 5px 10px; margin-right: 10px;">Back</button>
                </NuxtLink>
                <NuxtLink style="text-decoration: none;">
                    <button style="color: black; padding: 5px 10px; margin-right: 10px;">Active courses</button>
                </NuxtLink>
            </div>

            <table style="position: absolute; top: 320px; left: 80px; border-collapse: collapse;">
                <tr>
                    <td style="border: 1px solid black; width: 300px; height: 100px; color: black; text-align: center;">
                        <NuxtLink to="/academy/home_academy_instructor_courses_1">
                            <button style="width: 100%; height: 100%; background-color: transparent; border: none; outline: none; cursor: pointer;">
                                Course # 1
                            </button>
                        </NuxtLink>
                    </td>
                    <td style="border: 1px solid black; width: 300px; height: 100px; color: black; text-align: center;">2 Instructors, 4 Students</td>
                    <td style="border: 1px solid black; width: 300px; height: 100px; color: black; text-align: center;">Active</td>
                </tr>
                <tr>
                    <td style="border: 1px solid black; width: 300px; height: 100px; color: black; text-align: center;">
                        <NuxtLink to="/academy/home_academy_instructor_courses_2">
                            <button style="width: 100%; height: 100%; background-color: transparent; border: none; outline: none; cursor: pointer;">
                                Course # 2
                            </button>
                        </NuxtLink>
                    </td>
                    <td style="border: 1px solid black; width: 300px; height: 100px; color: black; text-align: center;">1 Instructor, 2 Students</td>
                    <td style="border: 1px solid black; width: 300px; height: 100px; color: black; text-align: center;">Active</td>
                </tr>
            </table>

            <NuxtImg
                src="/New_Logo-01.jpg"
                sizes="50vw sm:20vw" 
            />
            <div style="color: #4BA9C7; width: 15vw; font-size: 1vw; text-align: right;">DRONE SIMULATOR</div>
        </div>
    </NuxtLayout>
</template>
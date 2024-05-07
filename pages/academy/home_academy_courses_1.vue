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
                    <button style="color: black; background-color: white; border: 2px solid #4BA9C7; border-radius: 10px; padding: 5px 10px; margin-right: 10px;">Administrator</button>
                </NuxtLink>
                <button style="color: black; background-color: white; border: 2px solid black; border-radius: 10px; padding: 5px 10px;">Instructor</button>
            </div>

            <div style="position: absolute; top: 230px; left: 70px;">
    
                <NuxtLink to="/academy/home_academy_courses" style="text-decoration: none;">
                    <button style="color: black; padding: 5px 10px; margin-right: 250px;">Back</button>
                </NuxtLink>
                <NuxtLink style="text-decoration: none;">
                    <button style="color: #4BA9C7; padding: 5px 10px; margin-right: 10px;">+ Add student to course</button>
                </NuxtLink>
            </div>

            <table style="position: absolute; top: 320px; left: 380px; border-collapse: collapse;">
                <tr>
                    <td style="border: 1px solid black; width: 220px; height: 50px; color: black; text-align: center;">Juan C. Madrid</td>
                    <td style="border: 1px solid black; width: 220px; height: 50px; color: black; text-align: center;">Course # 1</td>
                    <td style="border: 1px solid black; width: 220px; height: 50px; color: black; text-align: center;">Active</td>
                </tr>
                <tr>
                    <td style="border: 1px solid black; width: 220px; height: 50px;color: black;text-align: center;">Camilo Guzmán</td>
                    <td style="border: 1px solid black; width: 220px; height: 50px;color: black;text-align: center;">Course # 1</td>
                    <td style="border: 1px solid black; width: 220px; height: 50px;color: black;text-align: center;">Active</td>
                </tr>
                <tr>
                    <td style="border: 1px solid black; width: 220px; height: 50px;color: black;text-align: center;">Javier Herrera</td>
                    <td style="border: 1px solid black; width: 220px; height: 50px;color: black;text-align: center;">Course # 1</td>
                    <td style="border: 1px solid black; width: 220px; height: 50px;color: black;text-align: center;">Active</td>
                </tr>
                <tr>
                    <td style="border: 1px solid black; width: 220px; height: 50px;color: black;text-align: center;">Juan P. Alvarado</td>
                    <td style="border: 1px solid black; width: 220px; height: 50px;color: black;text-align: center;">Course # 1</td>
                    <td style="border: 1px solid black; width: 220px; height: 50px;color: black;text-align: center;">Active</td>
                </tr>
            </table>

            <div style="position: absolute; top: 300px; left: 50px;">
                <p style="color: black; font-size: 1.5em; text-align: center; margin-bottom: 10px;"><strong>Course #1</strong></p>
            </div>

            <nuxt-link style="position: absolute; top: 340px; left: 55px; color: gray; font-size: 0.5em; text-align: center; padding: 5px 10px; cursor: pointer; text-decoration: none;">
                <strong>Edit course name</strong>
            </nuxt-link>

            <div style="position: absolute; top: 400px; left: 50px;">
                <p style="color: black; font-size: 1.5em; text-align: center; margin-bottom: 10px;"><strong>Instructors</strong></p>
            </div>

            <nuxt-link style="position: absolute; top: 430px; left: 200px; color: gray; font-size: 0.5em; text-align: center; padding: 5px 10px; cursor: pointer; text-decoration: none;">
                <strong>Edit</strong>
            </nuxt-link>

            <table style="position: absolute; top: 450px; left: 50px; border-collapse: collapse;">
                <tr>
                    <td style="border: 1px solid black; width: 220px; height: 50px; color: black; text-align: center;">Esteban Berón</td>
                </tr>
                <tr>
                    <td style="border: 1px solid black; width: 220px; height: 50px;color: black;text-align: center;">Jean Paul Sierra</td>>
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
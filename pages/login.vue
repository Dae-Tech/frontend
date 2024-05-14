<template>
    <NuxtLayout>
        <template #firstSpace>
            <NuxtLink class="boxHome" to="/"><button>Home Page</button></NuxtLink>
        </template>
        <div style="padding: 1vw; float: left;">
            <NuxtImg
                src="/New_Logo-01.jpg"
                sizes="100vw sm:30vw"
            />
            <div style="color: #4BA9C7; width: 30vw; font-size: 3vw; text-align: center;">DRONE SIMULATOR</div>
        </div>
        <div class="Log">
            <div class="logForm">E-mail</div>
            <input class="inputLog" type="email" placeholder="Type here">
            <div class="logForm">Password</div>
            <input class="inputLog" type="password" placeholder="Type here"><br>
            <NuxtLink to="/userHome"><input type="submit" value="Log in" class="boxLogin"></NuxtLink>
        </div>
    </NuxtLayout>
</template>

<style scoped>
    .boxHome {
        padding: 5px;
        margin: 5vh 13px 10px 13px;
        border: 4px solid white;
        background-color: #2D4C9A;
        width: 20vw;
        float: right;
        font-size: 25px;
        text-align: center;
        border-radius: 1vh;
        text-decoration: none;
    }
    .logForm {
        padding: 2vh 3vw 2vh 3vw;
        margin: 0vh 2vw 0vh 2vw;
        font-size: 3vh;
        width: 35vw;
        text-align: center;
    }
    .inputLog {
        width: 30vw;
        margin-left: 5vw;
        font-size: 2.5vh;
        border-radius: 2vh;
        padding-left: 0.5vw;
        height: 5vh;
        background-color: white;
    }
    .Log{
        float: right;
        margin-top: 5vh;
        margin-right: 3vw;
        background-color: #2D4C9A;
        height: 60vh;
        border-radius: 2vh;
    }
    .Log .boxLogin{
        float: none;
        margin: 20vh 4.5vw 2vh 4.5vw;
        padding: 0vh 2vw 0vh 2vw;
        width: 30vw;
        height: 7vh;
    }
</style>
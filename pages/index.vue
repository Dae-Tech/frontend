<template>
    <NuxtLayout>
        <template #firstSpace>
            <NuxtLink class="boxRegister" to="/registration"><button>Register</button></NuxtLink>
            <NuxtLink class="boxLogin" to="/login"><button>Log in</button></NuxtLink>
        </template>
        <div style="padding: 1vw;">
            <NuxtImg
                src="/New_Logo-01.jpg"
                sizes="100vw sm:30vw"
            />
            <div style="color: #4BA9C7; width: 30vw; font-size: 3vw; text-align: center;">DRONE SIMULATOR</div>
        </div>
    </NuxtLayout>
</template>

<style scoped>
    .boxLogin {
        padding: 5px;
        margin: 5vh 13px 10px 13px;
        border: 1px solid black;
        background-color: #4BA9C7;
        width: 25vw;
        float: right;
        font-size: 25px;
        text-align: center;
        border-radius: 1vh;
        color: black;
        text-decoration: none;
    }
    .boxRegister {
        padding: 5px;
        margin: 5vh 13px 10px 13px;
        border: 1px solid black;
        background-color: #4BA9C7;
        width: 20vw;
        float: right;
        font-size: 25px;
        text-align: center;
        border-radius: 1vh;
        color: black;
        text-decoration: none;
    }
</style>
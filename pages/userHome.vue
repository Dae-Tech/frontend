<template>
    <NuxtLayout>
        <template #firstSpace>
            <NuxtLink class="boxHome" to="/"><button>Log Out</button></NuxtLink>
            <div class="user">Pilot Name</div>
            <NuxtLink to="/userSubscription"><div class="sub">My subscription</div></NuxtLink>
        </template>
        <div class="accessSim"><b>ENTER SIMULATOR</b></div>
        <div>
            <NuxtImg
                    src="/New_Logo-01.jpg"
                    style="padding: 3vh 3vw 0vh 3vw; width: 30vw;"
            />
            <div style="color: #4BA9C7; width: 30vw; font-size: 2vw; text-align: center; padding: 0vh 3vw 3vh 3vw;">DRONE SIMULATOR</div>
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
        font-size: 3.5vh;
        text-align: center;
        border-radius: 1vh;
        text-decoration: none;
    }
    .user{
        float: right;
        font-size: 3vh;
        margin: 5vh 2vw 2vh 2vw;
    }
    .sub{
        float: right;
        font-size: 3vh;
        margin: 5vh 2vw 2vh 2vw;
    }
    .accessSim{
        float: right;
        padding: 5px;
        margin: 4vh 13px 4vh 13px;
        border: 1px solid black;
        box-shadow: -7px 7px 5px #3A3938;
        background-color: #2D4C9A;
        width: 25vw;
        font-size: 2vw;
        text-align: center;
        border-radius: 1vh;
        height: 8vh;
    }
</style>
  
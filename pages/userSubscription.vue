<template>
    <NuxtLayout>
        <template #firstSpace>
            <NuxtLink class="boxHome" to="/"><button>Log Out</button></NuxtLink>
            <div class="user">Pilot Name</div>
            <div class="sub">My subscription</div>
        </template>
        <div class="subscription">
            Subscribed since: 21/12/2023 <br>
            <br>
            Next payment: (Depende del plan)
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
    .user{
        float: right;
        font-size: 3vh;
        margin: 5vh 2vw 2vh 2vw;
    }
    .sub{
        font-size: 7vh;
        padding: 3vh 2vw 2vh 4vw;
    }
    .subscription{
        font-size: 5vh;
        padding: 6vh 3vw 2vh 4vw;
        color: black;
    }
</style>
<template>
    <NuxtLayout>
        <template #firstSpace>
            <h1 class="tittleFirstSpace">Register new individual account</h1>
            <NuxtLink class="boxHome" to="/"><button>Home Page</button></NuxtLink>
        </template>
        <section class="principalSpace">
            <div class="individualForm">Full name (first name and last name)</div>
            <input class="inputRegister" type="text" placeholder="Type here">
            <div class="individualForm">E-mail</div>
            <input class="inputRegister" type="email" placeholder="Type here">
            <div class="individualForm">Password</div>
            <input class="inputRegister" type="password" placeholder="Type here">
            <div class="individualForm">Confirm Password</div>
            <input class="inputRegister" type="password" placeholder="Type here">
            <div class="managementPolicy">I agree with information management policy <input type="checkbox"></div>
            <input type="submit" value="Register" class="registerBox">
        </section>
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
    .tittleFirstSpace {
        padding: 0px;
        margin: 5vh 13px 10px 13px;
        box-sizing: border-box;
        font-size: 5.5vh;
        width: 75vw;
        float: left;
        text-align: center;
    }
    .individualForm {
        padding: 2vh 3vw 2vh 3vw;
        margin: 0vh 2vw 0vh 1vw;
        font-size: 20px;
        color: black;
    }
    .inputRegister {
        width: 30vw;
        margin-left: 5vw;
        font-size: 2.5vh;
        border-radius: 2vh;
        padding-left: 0.5vw;
        height: 5vh;
    }
    .managementPolicy {
        font-size: 23px;
        padding: 8vh 7vw 0vh 35vw;
        color: black;
    }
    .registerBox {
        background-color: #2D4C9A;
        box-shadow: -7px 7px 5px #3A3938;
        border: 1px solid black;
        float: right;
        padding: 10px;
        margin: 2vh 4vw 10px 4vw;
        width: 20vw;
        border-radius: 2vh;
        font-size: 20px;
        text-decoration: none;
    }
</style>
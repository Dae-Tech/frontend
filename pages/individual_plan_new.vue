<template>
    <NuxtLayout>
        <template #firstSpace>
            <h1 class="tittleFirstSpace">Congratulations!<br>You're now registered</h1>
            <NuxtLink class="boxHome" to="/"><button>Home Page</button></NuxtLink>
        </template>
        <div class="planText">Select the subscription plan that best suits you!</div>
        <div class="btn-group groupPlan" role="group" aria-label="Basic radio toggle button group">
            <input type="radio" class="btn-check" name="btnradio" id="btnradio1" autocomplete="off">
            <label class="btn btn-outline-primary btnPlan" for="btnradio1"><h3>BASIC PLAN</h3><br>$300/month plan with monthly payments - cancel at anytime</label>
            
            <input type="radio" class="btn-check" name="btnradio" id="btnradio2" autocomplete="off">
            <label class="btn btn-outline-primary btnPlan" for="btnradio2"><h3>PRO PLAN</h3><br>$3300/month plan with monthly payments - cancel at anytime</label>
        
        </div>
        <input type="submit" value="Proceed to payment" class="paymentBox">
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
    .planText {
        padding: 4vh 0vw 2vh 0vw;
        font-size: 1.5vw;
        width: 100%;
        text-align: center;
    }
    .groupPlan{
        width: 100%;
        padding: 3vh;
    }
    .paymentBox {
        background-color: #4BA9C7;
        border: 1px solid black;
        float: right;
        padding: 10px;
        margin: 10vh 4vw 10px 10vw;
        width: 20vw;
        border-radius: 2vh;
        font-size: 20px;
    }
</style> 
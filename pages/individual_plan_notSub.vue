<template>
    <NuxtLayout>
        <template #firstSpace>
            <h1 class="tittleSecondSpace">You're not subscribed yet</h1>
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
    .tittleSecondSpace {
    padding: 0px;
    margin: 5vh 13px 10px 13px;
    box-sizing: border-box;
    font-size: 5.5vh;
    width: 75vw;
    float: left;
    text-align: center;
    }
</style>
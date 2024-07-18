<template>
  <NuxtLayout>
    <template #firstSpace>
      <div class="tittleFirstSpace">Subscribed</div>
      <NuxtLink class="boxHome" to="/"><button>Home Page</button></NuxtLink>
    </template>
    <div>
      <div class="check">Thank you for subscribing!</div>
      <NuxtImg
        format="gif"
        src="/Check.gif"
        style="padding: 3.5vh 3vw 0vh 3vw; width: 25vw; align-content: center; margin-left: 37.5vw;"
      />
      <div class="check1">Return to Home page.</div>
    </div>
  </NuxtLayout>
</template>

<style  scoped>
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
  .check{
    padding-left: 30vw;
    padding-right: 30vw;
    padding-top: 4vh;
    font-size: 4vh;
    text-align: center;
    color: black;
  }
  .check1{
    padding-left: 30vw;
    padding-right: 30vw;
    padding-top: 4vh;
    font-size: 4vh;
    text-align: center;
    color: black;
  }
</style>
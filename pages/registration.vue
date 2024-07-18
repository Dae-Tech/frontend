<template>
  <NuxtLayout>
    <template #firstSpace>
      <div class="tittleFirstSpace">Register new account</div>
      <NuxtLink class="boxHome" to="/"><button>Home Page</button></NuxtLink>
    </template>
    <div class="selectAccount">Select the type of account you would like to register:</div>
    <NuxtLink class="academyAccount" to="/register_academy"><button>I would like to register as an <div style="font-weight: bold;">Academy</div></button></NuxtLink>
    <NuxtLink class="individualAccount" to="/register_individual"><button>I would like to register as an <div style="font-weight: bold;">Individual</div></button></NuxtLink>
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
  .selectAccount{
    padding-left: 33vw;
    padding-right: 33vw;
    padding-top: 4vh;
    font-size: 35px;
    text-align: center;
    color: black;
  }
  .academyAccount{
    float: left;
    padding: 10px;
    margin: 15vh 10px 10px 16vw;
    box-shadow: -7px 7px 5px #3A3938;
    width: 26vw;
    border: 1px solid black;
    background-color: #2D4C9A;
    text-align: center;
    font-size: 29px;
    border-radius: 2vh;
  }
  .individualAccount{
    float: right;
    padding: 10px;
    margin: 15vh 16vw 10px 10px;
    box-shadow: -7px 7px 5px #3A3938;
    width: 26vw;
    border: 1px solid black;
    background-color: #4BA9C7;
    text-align: center;
    font-size: 29px;
    border-radius: 2vh;
    text-decoration: none;
  }
</style>
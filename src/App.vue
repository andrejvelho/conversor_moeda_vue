<template>
  <div class="div_center">
    <img alt="Vue logo" src="./assets/logo.png">
    <h2>Conversor de Moedas</h2>
  </div>
  <div class="linha">
    <Conversor moedaDe="USD" moedaPara="BRL" />
    <Conversor moedaDe="BRL" moedaPara="USD" />
  </div>
  <div class="linha">
    <Conversor moedaDe="EUR" moedaPara="BRL" />
    <Conversor moedaDe="BRL" moedaPara="EUR" />
  </div>
  <Footer/>
</template>

<script>

import Footer from './components/Footer.vue'
import Conversor from './components/Conversor.vue';

export default {
  name: 'App',
  components: {
    Conversor,
    Footer
  }
};
</script>

<style>

html,
body {
  margin: 0;
  padding: 0;
}

:root {
  --primary: #2a93d5;
  --black: #000000;
  --blackLighter: #9E9E9E;
  --grayLight: #F5F5F5;
  --grayMedium: #e5e5e5; 
  --white: #FFFFFF;
  --frontEnd: #6BD1FF;
  --backEnd: #00C86F;
}

#app {
  min-height: calc(100vh - var(--bodyPaddingTop));
  display: flex;
  flex-direction: column;
}

.linha{
  display: flex;
  justify-content: space-around;
  margin-top: 40px;
  margin-bottom: 40px;
}

 @media (max-width: 800px) {
   .linha {
     margin-bottom: 50px;
     display: grid;
   }
}

.div_center {
  text-align: center;
}

a {
  color: var(--backEnd);
}
</style>

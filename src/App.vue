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
</template>

<script>
import Conversor from './components/Conversor.vue';
export default {
  name: 'App',
  components: {
    Conversor
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
  max-width: 900px;
  margin: auto;
}

.linha{
  display: flex;
  justify-content: space-around;
  margin-top: 40px;
}

.div_center {
  text-align: center;
}
</style>

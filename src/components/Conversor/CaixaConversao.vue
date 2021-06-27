<template>
    <div class="linha">
      <Conversor v-bind:moedaDe="moeda1" v-bind:moedaPara="moeda2" />
      <Conversor v-bind:moedaDe="moeda2" v-bind:moedaPara="moeda1" />
    </div>
</template>

<script>
import Conversor from './Conversor.vue';

export default {
    name: 'CaixaConversao',
    props: ["moeda1" , "moeda2"],
    components: {
        Conversor
    }
}
</script>

<style>
    .linha{
        display: flex;
        justify-content: space-around;
        margin-top: 40px;
        margin-bottom: 40px;
    }
</style>
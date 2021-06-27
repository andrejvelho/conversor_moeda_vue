<template>
    <Header/>
    <CaixaConversao  moeda1="USD" moeda2="BRL"/>
    <CaixaConversao  moeda1="EUR" moeda2="BRL"/>
    <Footer/>
</template>

<script>
import Footer from './components/Footer/Footer.vue';
import Header from './components/Header/Header.vue'
import CaixaConversao from './components/Conversor/CaixaConversao.vue';

export default {
    name: 'Home',
    components: {
        Header,
        CaixaConversao,
        Footer
    }
}
</script>

<style>

</style>
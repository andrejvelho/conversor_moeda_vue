<template>
    <div class="conversor">
        <h2>{{moedaDe}} Para {{moedaPara}}</h2>
        <input type="text" v-model="moedaDeValue" v-bind:placeholder="moedaDe">
        <input type="button" v-on:click="converter" value="Converter">
        <h2>{{moedaParaValue}}</h2>
    </div>
</template>

<script>

export default {
    name: "Conversor",
    props: ["moedaDe" , "moedaPara"],
    data() {
        return {
            moedaDeValue : "",
            moedaParaValue : 0,
        }
    },
    methods: {
        converter() {
            let dePara = this.moedaDe+"_"+this.moedaPara;
            const URL_API = 'https://free.currconv.com/api/v7/convert?q='+dePara+'&compact=ultra&apiKey=0d6223d04ea490efdc5f';
            
            fetch(URL_API)
            .then(response => {return response.json()})
            .then(json => {
                let cotacao = json[dePara];
                this.moedaParaValue = this.moedaPara+' '+(cotacao * parseFloat(this.moedaDeValue) ).toFixed(2);
            })
        }
    }
};
</script>

<style scoped>
    .conversor {
        max-width: 300px;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        padding: 20px;
    }
</style>

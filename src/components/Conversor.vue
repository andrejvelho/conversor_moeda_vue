<template>
    <div class="conversor">
        <h2>{{moedaDe}} Para {{moedaPara}}</h2>
        <input type="tel" v-model="moedaDeValue" @focus="selectAll" ref="input" v-on:keypress="isNumber($event)" v-bind:placeholder="moedaDe">
        <input type="button" v-on:click="converter" class="btn_primary"  value="Converter">
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
                this.moedaParaValue = this.moedaPara+' '+(cotacao * parseFloat(this.moedaDeValue) ).toFixed(3);
            })
        },
        selectAll() {
           this.$refs.input.select();
        },
        isNumber: function(event) {
            event = (event) ? event : window.event;
            var charCode = (event.which) ? event.which : event.keyCode;
            console.log(charCode);
            if ((charCode > 31 && (charCode < 48 || charCode > 57)) 
                    && charCode !== 46 
                    && charCode !== 13 
                    && charCode !== 44) {
                event.preventDefault();
            } else if(charCode === 13) {
                this.converter();
                return true;
            } else if (charCode === 44) {             
                this.moedaDeValue = this.moedaDeValue+'.';
                event.preventDefault();
            } else {
                return true;
            }
        }
    }
};
</script>

<style scoped>
    .conversor {
        max-width: 300px;
        box-shadow: 0 4px 8px rgba(42 147 213);
        padding: 20px;
        border-radius: 6px;
    }

    .btn_primary {
        color: #fff;
        background-color: var(--primary);
        border-color:  var(--primary);
        border-radius: 3px;
    }
</style>

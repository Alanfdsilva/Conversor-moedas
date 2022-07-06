<template>
    <div class="conversor p-5">
        <h3>{{moedaA}} to {{moedaB}}</h3>
        <input type="number" v-model="moedaA_value" :placeholder="moedaA" class="p-1">
        <button value="Converter" v-on:click="converter" class="m-2 btn btn-outline-success">Converter</button>
        <h1>{{moedaB_value}}</h1>
    </div>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
    name: "Conversor_app",
    props: ['moedaA', 'moedaB'],
    data() {
        return {
            moedaA_value: '',
            moedaB_value: 0
        }
    },
    methods: {
        converter () {
            let moedaA_moedaB = this.moedaA + '_' + this.moedaB;
            let url = 'https://free.currconv.com/api/v7/convert?q='+ moedaA_moedaB + '&compact=ultra&apiKey=945eba85d98da601cd30'
            fetch(url).then(res=>{return res.json()}).then(json=> {
                let cotacao = json[moedaA_moedaB];
                this.moedaB_value = (cotacao * parseFloat(this.moedaA_value)).toFixed(2);
            })
        }
    }
})
</script>

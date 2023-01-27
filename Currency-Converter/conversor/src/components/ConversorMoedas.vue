<template>
    <div class="conversor-moedas">
        <h2>{{ moedaA }} para {{ moedaB }}</h2>
        <input type="text" v-bind:placeholder="moedaA" v-model="moedaA_value">
        <input type="button" value="Converter" v-on:click="converter">
        <h2>{{ moedaB_value }}</h2>
    </div>
</template>

<script>
export default {
    name: "ConversorMoedas",
    props: ["moedaA", "moedaB"],
    data() {
        return {
            moedaA_value: "",
            moedaB_value: 0
        };
    },
    methods: {
        converter() {
            let url = "https://api.freecurrencyapi.com/v1/latest?apikey=t7DtyG7rpgPH1XWr1u03Z2FsREL65QdzUF3UcjxO&currencies=" + this.moedaB + "&base_currency=" + this.moedaA;

            fetch(url)
                .then(res => {
                    return res.json()
                })
                .then(json => {
                    let cotacao = json["data"][this.moedaB];
                    this.moedaB_value = (cotacao * parseFloat(this.moedaA_value)).toFixed(2);
                });
        }
    }
};
</script>

<style scoped>
.conversor-moedas {
    max-width: 300px;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
    padding: 20px;
}
</style>
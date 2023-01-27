<template>
  <div id="app">
    <h1>Conversor de Moedas</h1>
    <div class="linha">
      <ConversorMoedas moeda-a="USD" moeda-b="BRL" />
      <ConversorMoedas moeda-a="BRL" moeda-b="USD" />
    </div>
    <div class="linha">
      <ConversorMoedas moeda-a="CAD" moeda-b="BRL" />
      <ConversorMoedas moeda-a="BRL" moeda-b="CAD" />
    </div>
    <div class="linha">
      <ConversorMoedas moeda-a="EUR" moeda-b="BRL" />
      <ConversorMoedas moeda-a="BRL" moeda-b="EUR" />
    </div>
  </div>
</template>

<script>
import ConversorMoedas from "./components/ConversorMoedas.vue"
export default {
  name: 'app',
  components: {
    ConversorMoedas
  }
};
</script>

<style>
#app {
  max-width: 900px;
  margin: auto;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.linha {
  display: flex;
  justify-content: space-around;
  margin-top: 40px;
}
</style>
<template>
  <div class="app">
    <h1>Conversor de moedas</h1>
    <div class="linha">
      <Conversor moeda-a="USD" moeda-b="BRL" />
      <Conversor moeda-a="BRL" moeda-b="USD" />
    </div>
    <div class="linha">
      <Conversor moeda-a="CAD" moeda-b="BRL" />
      <Conversor moeda-a="BRL" moeda-b="CAD" />
    </div>
    <div class="linha">
      <Conversor moeda-a="EUR" moeda-b="BRL" />
      <Conversor moeda-a="BRL" moeda-b="EUR" />
    </div>
  </div>
</template>

<script>
import Conversor from './components/Conversor.vue'

export default {
  name:'app',
  components: { 
    Conversor
  }
};

</script>

<style scoped>
.app {
  margin: auto;
  max-width: 900px;
  font-family: "Avenir", Arial, Helvetica, sans-serif;
  text-align: center;
  margin-top: 60px;
}
.linha {
  margin-top: 40px;
  display: flex;
  justify-content: space-around;
}

@media (max-width: 616px) {
    .app {
      display:flex;   
      flex-direction: column;
      flex-wrap:wrap;
    }
} 
</style>
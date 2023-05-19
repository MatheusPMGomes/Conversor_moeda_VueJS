<template>
  <div id="app">
    <img loading="lazy" src="../public/background.jpg" alt="">
    <h1>Conversor de moedas VueJS</h1>
    <div class="linha">
      <Conversor  moeda-a="USD" moeda-b="BRL"/>
      <Conversor  moeda-a="BRL" moeda-b="USD"/>
    </div>
    <div class="linha">
      <Conversor  moeda-a="CAD" moeda-b="BRL"/>
      <Conversor  moeda-a="BRL" moeda-b="CAD"/>
    </div>
    <div class="linha">
      <Conversor  moeda-a="EUR" moeda-b="BRL"/>
      <Conversor  moeda-a="BRL" moeda-b="EUR"/>
    </div>
  </div>
</template>

<script>
import Conversor from "./components/Conversor.vue"

export default {
  name: 'App',
  components: {
    Conversor
  }
}
</script>

<style>

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

h1{
  color: white;
  margin-top: 1em;
}

img{
  position: fixed;
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
  z-index: -1;
  background-image: url(../public/background.jpg);
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.linha{
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  margin: 40px 0;
  gap: 1em;
}
</style>

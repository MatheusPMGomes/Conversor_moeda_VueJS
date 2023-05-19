<template>
    <div class="conversor">
      <h2>{{ moedaA }} para {{ moedaB }}</h2>
      <input type="number" v-model="moedaA_value" :placeholder="moedaA">
      <input type="button" @click="converter" value="Converter">
      <h2>{{ moedaB_value }}{{ moedaB }}</h2>
    </div>
  </template>
  
  <script>
  export default {
    name: "ConversorMoeda",
    props: ["moedaA", "moedaB"],
    data() {
      return {
        moedaA_value: "",
        moedaB_value: 0
      };
    },
    methods: {
      converter() {  
        let url =
          "https://api.freecurrencyapi.com/v1/latest?apikey=9MBBGvs0BAiQM7D9dgEQr9lk1XjA5mPd6cmnRIiS&currencies=" +
          this.moedaB +
          "&base_currency=" +
          this.moedaA;
  
        fetch(url)
          .then((res) => res.json())
          .then((json) => {
            let cotacao = json.data[this.moedaB]
            this.moedaB_value = (cotacao*this.moedaA_value).toFixed(2)
          });
      }
    }
  };
  </script>
  
  <style scoped>

  .conversor{
    background-color: white;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 1);
    padding: 20px;
    background: rgba(255, 255, 255, 0.2);
    box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
    backdrop-filter: blur(5px);
    -webkit-backdrop-filter: blur(5px);
    border: 1px solid rgba(255, 255, 255, 0.3);
    text-shadow: #000000 2px 2px 1px;
    color: white;
  }
  
  </style>
  
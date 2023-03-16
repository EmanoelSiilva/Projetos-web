<template>
  <h1>Cálculo IMC</h1>
  <div class="mainDiv">
    <div class="getInfo">
      <label for="">Nome</label>
      <input type="text" v-model="name">
      <label for="">Peso</label>
      <input type="text" v-model="peso">
      <label for="">Altura</label>
      <input type="text" v-model="altura">
      <button @click="calculaIMC()">Calcular IMC</button>
    </div>

    <div class="resultDiv">
      <span>
        <p v-if="this.imc != ''">Olá {{ name }}! O seu IMC é de {{ imc }}</p>
      </span>
    </div>
    
  </div>

</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      name: '',
      altura: 0,
      peso: 0,
      imc: ''
    }
  },
  methods: {
    calculaIMC() {
      const imc = this.peso / Math.pow(this.altura, 2)
      this.imc = imc.toFixed(2)
      console.log(this.imc)
    }
  }
}
</script>

<style>
  h1 {
    text-align: center;
  }
  
  .getInfo {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .getInfo input {
    width: 250px;
  }

  .getInfo button {
    border-radius: 25px;
    margin: 20px;
  }
  .mainDiv {
    border: 1px solid #9359c988;
    padding: 5px;
    margin: 10px;
    padding: 10px;
  }

  .resultDiv {
    border: 1px solid #9359c988;
    padding: 5px;
    margin: 10px;
    height: 70px;
  }
</style>

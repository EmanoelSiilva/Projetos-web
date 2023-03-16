<template>
  <h2>Formulário</h2>
  <div class="mainDiv">
    <div>
      <label >Nome completo:</label>
      <input type="text" class="fullName" v-model="fullName">
      
      <button @click="splitName" class="btn">>>></button>
    </div>

    <div class="divSplitName">
      <p>Nome</p>
      <input type="text" class="inputSplit" :value="firstName">
      <p>Sobrenome</p>
      <input type="text" class="inputSplit" :value="lastName">
    </div>
  </div>
</template>

<script>


export default {
  name: 'App',
  data() {
    return {
      fullName: '',
      firstName: [],
      lastName: []
    }
  },
  components: {
    
  },
  methods: {
    splitName() {
      this.firstName = this.fullName.split(" ")[0]
      this.lastName = this.fullName.split(" ")[1]
      console.log(this.firstName + ' ' + this.lastName) 
    }
  }
}
</script>



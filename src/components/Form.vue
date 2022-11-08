<template>
  <div>
    <h2>Digite o seu CEP</h2>
    <p>Não utilize nº de casa/ apto/ lote/ <br>prédio ou abreviatura</p>
    <input />
  </div>
</template>

<script>

import input from './input.vue';

export default {
  name: 'Form',
  components:{
    input
  },
}
</script>

<style scoped>
  h2{
    margin-left: 2%;
    font-family: arial;
    color:rgb(30, 134, 231)
  }

  p{
    margin-left: 2%;
    font-family: arial;
    color:rgb(30, 134, 231)
  }
</style>

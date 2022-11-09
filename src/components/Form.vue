<template>
  <div>
    <h2>Consulte o seu endereço com o seu CEP</h2>
    <p>Não utilize nº de casa/ apto/ lote/ <br>prédio ou abreviatura</p>
    <div class="frm-row">
      <label for="cep">CEP</label>
      <input />
    </div>

    <div class="frm-row">
      <label for="cep">Rua</label>
      <input />
    </div>

    <div class="frm-row">
      <label for="cep">Bairro</label>
      <input />
    </div>  

    <div class="frm-row">
      <label for="cep">Cidade</label>
      <input />
    </div>  

    <div class="frm-row">
      <label for="cep">Estado</label>
      <input />
    </div>

  </div>
</template>

<script>

import input from './input.vue';

export default {
  name: 'Form',
  components:{
    input
  }
}
</script>

<style scoped>
label{
  font-family: arial;
  margin-left: 2%;
}


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

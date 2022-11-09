<template>
  <div>
    <h2>Consulte o seu endereço com o seu CEP</h2>
    <p>Não utilize nº de casa/ apto/ lote/ <br>prédio ou abreviatura</p>
    <form>
      <div class="frm-row">
          <label for="cep">CEP</label>
          <input type="text"  v-model="cep"  v-on:change="consulta_cep" id="cep" maxlength="8" >
      </div>
      <!--<div class="frm-row">
          <label for="rua">Rua</label>
          <input type="text" id="rua" > 
          {{ cep_data.logradouro}}
      </div>
      <div class="frm-row">
          <label for="bairro">Bairro</label>
          <input type="text" id="bairro" >
      </div>  
      <div class="frm-row">
          <label for="cidade">Cidade</label>   
          <input type="text" id="cidade"> 
          
      </div>  
      <div class="frm-row">
          <label for="estado">Estado</label>
          <input type="text"  id="estado" >
      </div>!-->

      <div v-if="cep_data != null">
        Logradouro: {{cep_data.logradouro}}
      </div>
    </form>
  </div>
</template>

<script>
import { assertExpressionStatement } from '@babel/types';


export default {
  name: 'Form',
  data(){

    return{
      cep: "",
      cep_data: null
    }
  },
  methods:{
    consulta_cep(){
      var self = this;

      axios.get('https://viacep.com.br/ws/'+this.cep+'/json/')
      .then(function (response) {

        console.log(response);
        self.cep_data = response.data;

      })
      .catch(function (error){

        //console.log(error);
      })
      .finally(function () {

      });
    }
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

  input{
    padding: 10px;
    border-radius: 5px;
    border: 1px solid #fff;
    display: block;
    background-color: rgb(206, 205, 205);
    width: calc(100% - 110px);
    margin-left: 4%;
    margin-bottom: 15px;
}
</style>

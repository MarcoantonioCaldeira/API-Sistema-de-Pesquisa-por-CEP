<template>
  <div id="app">
    <h2>Consulte o seu endereço com o seu CEP</h2>
    <p>Não utilize nº de casa/ apto/ lote/ <br>prédio ou abreviatura</p>
    <br><br>
    <label>CEP</label>
    <input type="text" v-model="cep" v-on:change="consulta_cep" maxlength="8">
    <div v-if="cep_data != null ">
        Bairro: {{cep_data.bairro}}
        Cidade: {{cep_data.localidade}}
        Estado: {{cep_data.uf}}
    </div>
  </div>
</template>

<script>
 import axios from "axios";
import { assertExpressionStatement } from '@babel/types';

export default {
  name: 'Form',
  data(){

    return{
        cep: "",
        cep_data: null,
        cep_keys : []
      }
  },
  methods: {
    consulta_cep(){
      var self = this;

      axios
      .get('https://viacep.com.br/ws/'+this.cep+'/json/')
      .then(function (response) {

        console.log(response);
        self.cep_data = response.data;

        self.cep_keys = Object.keys( self.cep_data );

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

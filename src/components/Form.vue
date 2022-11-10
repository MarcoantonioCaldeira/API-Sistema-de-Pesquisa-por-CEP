<template>
  <div id="app">
    <h2 class="titulo">Consulte o seu endereço com o seu CEP</h2>
    <p>Não utilize nº de casa/ apto/ lote/ <br>prédio ou abreviatura</p>
    <br><br>
    <input type="text" v-model="cep" v-on:change="consulta_cep" maxlength="8" placeholder="CEP">
    <div id="resultado" v-if="cep_data != null ">
  
        <h2>Rua: </h2> {{cep_data.logradouro}}
        <h2>Bairro:</h2> {{cep_data.bairro}}
        <h2>Cidade:</h2> {{cep_data.localidade}}
        <h2>Estado:</h2> {{cep_data.uf}}
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

*{
  font-family: arial;
}


  h2{
    font-family: arial;
    color:rgb(30, 134, 231)
  }

  .titulo{
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
    margin-left: 2%;
    margin-bottom: 15px;
}

  #resultado{
    width: calc(101% - 110px);
    height: 500px;
    background-color: rgb(206, 205, 205);
    margin-left: 2%;
    border-radius: 5px;
  }
</style>

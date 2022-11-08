<template>
  <div id="components">
    <Form />
  </div>
</template>

<script>

import Form from './components/Form.vue'

export default {
  name: 'App',
  components: {
    Form
  }
}
</script>

<style>
#components{
  width: 30%;
  height: 160px;
  background-color: rgb(223, 216, 203);
  margin-top: 20%;
  margin-left: 34%;
  border-radius: 5px;
}
</style>

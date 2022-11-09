<template>
    <div class="frm-row">
        <input type="text"  name="cep" id="cep"/>
    </div>   
</template>

<script>
export default{
    name: 'input'
}

let cep = document.querySelector('#cep');

cep.value = '0509593450';

cep.addEventListener('blur', function(e){
    let cep = e.target.value;
    let script = document.createElement('script');
    script.src = 'https://viacep.com.br/ws/01001000/json/?callback=callback_name'
})

</script>
<style>

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
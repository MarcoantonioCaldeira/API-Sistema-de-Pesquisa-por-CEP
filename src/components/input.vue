<template>
    <div class="frm-row">
        <input type="text"  name="cep" id="cep" maxlength="8"/>
    </div>   
</template>

<script>
export default{
    name: 'input'
}


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
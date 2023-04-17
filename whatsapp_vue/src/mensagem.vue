<template>
    <div class="mensagem" v-bind:class="{verde: verde}">
        {{conteudo}}
        <span>{{horario}}</span>
    </div>
</template>
<script>
    export default {
        props: ['conteudo', 'horario', 'verde']
    }
</script>
<style>
    div.verde{
        background: #008000;
    }
    div.mensagem{
        font-size: 14px;
        box-shadow: rgba(0, 0, 0, .13) 0px 1px .5px 0px;
        background: #ffffff;
        margin: 5px 100px;
        padding: 5px 10px;
        border-radius: 5px;
        width: fit-content;
    }
    div.mensagem span{
        margin-left: 25px;
        font-size: 11px;
        color: #808080;
    }
</style>
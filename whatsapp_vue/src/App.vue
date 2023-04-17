<template>
  <div>
    <section class="section">
      <div class="container">
        <div class="columns">
          <div class="column is-3 lista-de-conversas">
            <div class="barra-superior" />
            <div class="item" v-for="conversa, index in conversas" v-bind:key="index" @click="indiceAtivo = index">
              <div class="title is-6">
                {{ conversa.usuario }}
              </div>
              <div class="subtittle is-6">
                Última Mensagem...
              </div>
            </div>
          </div>
          <div class="column conversa-ativa">
            <div class="barra-superior">
              <span>{{conversas[indiceAtivo].usuario}}</span>
            </div>
            <Mensagem
              v-for="(mensagem, indice) in conversas[indiceAtivo].mensagens"
              v-bind:key="indice"
              :conteudo="mensagem.conteudo"
              :horario="mensagem.horario"
              :verde="mensagem.verde"
            />
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
  import conversasIniciais from './dados.js'
  import Mensagem from './mensagem.vue'

  export default {
    data: function(){
      return{
        conversas: conversasIniciais,
        indiceAtivo: 0
      }
    },
    components: {
      Mensagem
    }
  }
</script>

<style>
  div.columns{
    min-height: 800px;
    box-shadow: 0 3rem 3rem -1rem rgba(10, 10, 10, .2);
  }
  div.column{
    padding: 0;
  }
  div.lista-de-conversas{
    background: #ffffff;
  }
  div.conversa-ativa{
    background: #e5ddd5;
  }
  div.barra-superior{
    margin: 0;
    height: 50px;
    background: #ededed;
    border-right: 1px solid #e1e1e1;
    border-bottom: 1px solid rgb(200, 200, 200);
  }
  div.barra-superior span{
    line-height: 50px;
    margin-left: 25px;
    font-weight: 500;
  }
  div.item{
    border-bottom: 1px solid #f2f2f2;
    padding: 15px 30px;
    margin-bottom: 0 !important;
  }
  div.subtittle{
    color: #808080;
  }
  div.item:hover{
    background: #f5f5f5;
    cursor: pointer;
  }
</style>
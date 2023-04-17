<template>
  <div>
    <section class="section">
      <div class="container">
        <div class="columns">
          <div class="column is-3 lista-de-conversas">
            <div class="barra-superior" />
            <p v-for="conversa in conversas">{{conversa}}</p>
          </div>
          <div class="column conversa-ativa">
            <div class="barra-superior">
              <span>Usuário</span>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
  import conversasIniciais from '/dados.js';

  export default {
    data: function(){
      return{
        conversas: conversasIniciais
      }
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
</style>
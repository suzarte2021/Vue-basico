<template>
  <div class="container">
    <div class="row">
      <div class="col-sm-12">
        <h1 class="titulo">Adicionar produto</h1>
        <hr />
      </div>
    </div>

    <div class="row formulario">
      <div class=" row folha">

        <div class="col-sm-12">
          <div class="form-group">
            <label for="nome">Nome</label>
            <input id="nome" type="text" class="form-control" />
          </div>
        </div>

        <div class="col-sm-4">
          <div class="form-group">
            <label for="quantidade">Quantidade</label>
            <input id="quantidade" type="text" class="form-control" />
          </div>
        </div>

        <div class="col-sm-4">
          <div class="form-group">
            <label for="valor">Valor</label>
            <input id="valor" type="text" class="form-control" />
          </div>
        </div>

        <div class="col-sm-4">
          <div class="form-group">
            <label for="data-cadastro">Data de cadastro</label>
            <input id="data-cadastro" type="text" class="form-control" />
          </div>
        </div>

        <div class="col-sm-12">
          <div class="col-sm-2">
            <Button :callback="salvarProduto" value="Salvar"></Button>
            
          </div>
          <div class="col-sm-2">
            <Button :callback="cancelar" value="Cancelar"></Button>
          </div>
   

        </div>

      </div>
    </div>
  </div>
</template>
<script>
// import Input from '../components/input/Input.vue';
import Button from '../components/button/Button.vue';

export default {
  name: "Produto",
  components: {
    Button,
    // Input
  },
  data() {
    return {
      mensagem: "Estou na tela de cadastro de produto",
    };
  },
};
</script>
<style scoped>
.formulario {
  max-width: 550px;
}
</style>

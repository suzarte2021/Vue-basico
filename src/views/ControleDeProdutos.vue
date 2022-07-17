<template>
  <div class="container">

    <div class="row"> <!--Linha Boot-->
      <div class="col-sm-12"> <!--Declarando uma linha com 12 colunas-->
        <h2 class="titulo">Produtos</h2>
        <hr>
      </div>
    </div>

    <div class="row sub-cointainer"> <!--Container-->
        <div class="col-sm-3">
          <Button :callback="adicionarProduto" value="Adicionar"></Button>
        </div>
    </div>

    <div class="row">
      <div class="col-sm-12">
        <table class="table table-hover">
          <thead>
            <tr>
              <th>Código</th>
              <th>Nome</th>
              <th>Quantidade</th>
              <th>Valor</th>
              <th>Data de cadastro</th>
              <th></th> <!--São as colunas da tabela-->
            </tr>
          </thead>
          <tbody>
            <tr v-for="item in produtos" :key="item.id">
              <td>{{ item.id }}</td>
              <td>{{ item.nome }}</td>
              <td>{{ item.quantidadeEstoque }}</td>
              <td>{{ item.valor | real }}</td>
              <td>{{ item.dataCadastro | data }}</td>
              <td>Editar / Excluir</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
    
  </div>
</template>
<script>

import Button from '../components/button/Button.vue'; //*Importando*//
import produtoService from '@/services/produto-service';
import Produto from "../models/Produto";
import conversorDeData from '../utils/conversor-data';
import conversorMonetario from '../utils/conversor-monetario';

export default {
  name:"ControleDeProdutos",
  components:{ //Registrar o componente que vai usar//
    Button
  },
  filters:{
    data(data){
      return conversorDeData.aplicarMascaraDataHoraEmDataIso(data);
    },
    real(valor) {
      return conversorMonetario.aplicarMascaraParaRealComPrefixo(valor);
    }
  },
  data(){
    return {
      produtos: []
    }
  },
  methods:{

    adicionarProduto(){
      this.$router.push({name:'NovoProduto'})
    },

    editarProduto(produto){
      console.log(produto);
      this.$router.push({name:'EditarProduto'})
    },
    obterTodosOsProdutos(){

      produtoService.obterTodos()
      .then(response => {
        this.produtos = response.data.map(p => new Produto(p));
      })
      .catch(error => {
        console.log(error);
      })
    }
  },

  mounted(){
    this.obterTodosOsProdutos();
  }
  
}
</script>
<style scoped>

</style>

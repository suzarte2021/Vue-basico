<template>
    <div class="box-login">

        <div class="logo">  <!---->
            <h1>Login</h1>
        </div>

        <Input
          label="E-mail" 
          placeHolder="exemplo@exemplo.com"
        ></Input> <!--Chamando o componente Input-->
        
        <Input
          label="Senha"
          placeHolder="123456"   
          type="password" 
        ></Input>

        <Button value="Entrar" :callback="login"></Button>  
    
    </div>
</template>
<script>
import Input from '../components/input/Input.vue';
import Button from '../components/button/Button.vue';

export default {
  name:"Login",
  components:{
    Input,
    Button
  },
  data(){
    return {

    }
  },
  methods:{
    login(){ 
      // Aqui criar uma logica para acessar o sistema
      this.$router.push({name:'Dashboard'})
    }
  }
}
</script>

<style scoped> 
                          /*Definindo campo de Input tela de Login/*/ 
  .box-login {
    width: 300px;                /*Definindo largura da tela de Login*/
    margin: auto;                /*Definindo a margin da tela de Login*/
    border: 1px solid #ddd;   /*Definindo bordura da tela de Login*/
    margin-top: 70px;           /*Definindo margin tela de Login/*/
    padding: 30px;              /*Definindo espaçamento entre as bordas de margin tela de Login/*/ 
  }

  .logo {
    text-align: center;
    color: var(--cor-primaria);
    font-size: 22px;
    
  }
</style>

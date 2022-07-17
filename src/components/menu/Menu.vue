<template>
    <ul class="menu">
        <li>
            <a @click="() => this.$router.push({path:'/'})">Dashboard</a>  <!--Botão Clicar-->
        </li>              <!--Path ele vai para a rota Dashboard-->
        <li>
            <a @click="() => this.$router.push({path:'/controle-de-produtos'})">Produtos</a> <!--Adicionando botão controle de produtos-->
        </li> <!--Path ele vai para a rota controle de produtos-->
        <li>
            <a @click="() => this.$router.push({path:'/controle-de-clientes'})">Clientes</a> <!--Adicionando botão clientes-->
        </li>  <!--Path ele vai para a rota controle de clientes-->
        <li>
            <a @click="() => this.$router.push({path:'/login'})">Sair</a>  <!--Adicionando botão de Sair-->
        </li> <!--Path ele vai para a rota login-->
    </ul>
</template>
<style scoped>

    ul{
        list-style-type: none;
        margin: 0;
        padding: 0;
        overflow: hidden;
        background-color: var(--cor-primaria);
    }

    li {
        float: left;
    }

    li:first-child{
        margin-left: 40px;
    }

    li:last-child{
        float: right;
        margin-right: 10px;
    }

    ul.menu li a {
        display: block;
        color: #FFF;
        padding: 15px 17px;
        text-decoration: none;
        text-align: center;
        cursor: pointer;
    }

    li a:hover{
        background-color: var(--cor-secundaria);
    }

</style>
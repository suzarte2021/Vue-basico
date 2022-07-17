<template>
    <div >       
        <label for=""> {{ label }}</label> <br>
        <input :placeholder="placeHolder" :type="type">
    </div>
</template>
<script>
export default {
    name:"Input",
    props:{           /*Para armagenar as informações */
        label: { type: String, default: ''}, /*Toda vez que eu for usar Input, tenho que passar uma Lei do tipo String para que não ocorra erro*/     
        type: { type: String, default: 'text'}, /*Adicionando dentro do Type um Objeto*/ 
        placeHolder: { type: String, default: ''}, /*PlaceHolder Padrão JavaScript*/
    }
}
</script>
<style scoped>

input { 
    width: 100%;                      /*Definindo largura do tamanho do bloco tela de Login*/
    padding: 12px 20px;              /*Definindo a largura e profundidade da tela de Login*/
    margin: 8px 0px;                 /*Definindo margin tela de Login/*/
    display: inline-block;           /*Definindo display tela de Login/*/
    border: 1px solid #ddd;        /*Definindo borda tela de Login/*/
    outline: none;                   /*Definindo/removendo marca de tela de Login/*/
    border-radius: 4px;              /*Definindo borda redondada /*/
    box-sizing: border-box;          /*Liberando a borda tela de Login/*/
}
</style>
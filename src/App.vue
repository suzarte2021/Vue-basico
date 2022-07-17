<template>
  <div id="app">
    <Menu v-if="this.$router.currentRoute.name != 'Login'"></Menu>
    <router-view/>
  </div>
</template>
<script>

import Menu from "@/components/menu/Menu.vue";

export default {
  components:{
    Menu
  }
}
</script>

<style>

  @import url('https://fonts.googleapis.com/css2?family=Quicksand:wght@300;400;500;600;700&display=swap');

  :root{
    --cor-primaria: #0099ff;
    --cor-secundaria: #FF6E40;
  }

  body {
    margin: 0;
    padding: 0;
    font-family: 'Quicksand', sans-serif;
  }

  .container {
    margin-top: 15px;
  }

  .titulo {
    font-weight: 600;
    color: #363636;
    font-size: 25px;
  }

  hr{
    margin: 0;
  }

  .sub-cointainer{
    margin-top: 15px;
  }

</style>

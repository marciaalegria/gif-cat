<template>
    <div class="container">
        <div class="titulo" id="app">
            <hijo></hijo>
        </div>
        <div class="formulario">
  
        </div>
        <div class="result">
            
        </div>
    </div>

</template>

<script>
import Hijo from "./components/Hijo.vue";
  export default {
    data() {
      return {
        message: 'Random Gif-Cat',
      };
    },
    components:{
        'hijo': Hijo,
    }
  }
</script>

<style scoped>
  .titulo {
    font-family: "Calibri", sans-serif;
    color: darkblue;
    background: lightblue;
  }
  .formulario{
    background: rgb(241, 139, 144);
  }
  .result{
    background: lightblue;
  }
</style>
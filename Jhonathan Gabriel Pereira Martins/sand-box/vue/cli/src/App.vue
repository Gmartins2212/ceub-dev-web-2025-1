<template>
  <div>
    <h1>VUE</h1>
    <br>
    <home-component/>
    <br>
    <usuario-component/>
    <br>
    <imagem-component 
        @visibilidadeImg="alertaPalmeiras"
        nomeBotao="Aparece Palmeiras" 
        urlImagem="data:image/jpeg;base64,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"/>
    <imagem-component 
        @visibilidadeImg="alertaBotafogo"
        nomeBotao="Aparece Botafogo" 
        :urlImagem="urlBanner"/>
    <br>
    <estilo-component/>
  </div>
</template>

<script>
import HomeComponent from './components/HomeComponent.vue'
import UsuarioComponent from './components/UsuarioComponent.vue';
import ImagemComponent from './components/ImagemComponent.vue';
import EstiloComponent from './components/EstiloComponent.vue';

export default {
  name: 'App',
  components: {
    HomeComponent,
    UsuarioComponent,
    ImagemComponent,
    EstiloComponent
  },
  data() {
    return {
      urlBanner : "data:image/png;base64,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"
    }
  },
  methods: {
    alertaPalmeiras(isVisivel){
      if(isVisivel){
        alert("Palmeiras visivel");
      }
    },
    alertaBotafogo(isVisivel) {
      if(isVisivel){
        alert("Botafogo visivel");
      }
    }
  },
  created() {
    console.log("created");
  },
  mounted() {
    console.log("mounted");
  },
  updated(){
    console.log("updated");
  },
  errorCaptured() {
    console.log("errorCaptured");
  },
  unmounted(){
    console.log("unmounted");
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: start;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

<template>
  <Navbar :logo="logo_src" :alt="app_name" />
  <router-view />
  <Footer />

</template>

<script>
import Navbar from './components/Navbar';
import Footer from './components/Footer.vue';

export default {
  components: {
    Navbar,
    Footer,
  },
  data() {
    return{
      logo_src: "/img/logo.png",
      app_name:"Monte Seu Burguer"
    }
  }
}
</script>

<style>

  @import url('https://fonts.googleapis.com/css2?family=Roboto&display=swap');

  * {
    font-family: 'Roboto', sans-serif;
    padding: 0;
    margin: 0;
    box-sizing: border-box;
    }

  html{
    font-size: 63,5%;
  }

  main {
    margin-top: 20px;
    min-height: 100%;
    display: block;
    min-height: 100vh;
    min-height: -webkit-calc(100vh - 100px);
    min-height: -moz-calc(100vh - 100px);
    min-height: calc(100vh - 100px);
    position: relative;
    width: 100%;
    scroll-behavior: smooth;
    background-color: #FECE00;
  }

  h1 {
    text-align: center;
    font-size: 42px;
    margin-bottom: 30px;
    color: #222;
  }

</style>

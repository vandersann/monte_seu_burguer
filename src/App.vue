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
  * {
    font-family: Arial, Helvetica, sans-serif;
    padding: 0;
    margin: 0;
    box-sizing: border-box;
    }

  main {
    margin: 50px;
    min-height: 350px;
  }

  h1 {
    text-align: center;
    font-size: 42px;
    margin-bottom: 30px;
    color: #222;
  }

</style>

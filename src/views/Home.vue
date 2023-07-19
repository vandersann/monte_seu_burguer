<template>
  <Banner />
  <main>
    <h1>Monte o seu burguer:</h1>
    <BurguerForm />
  </main>
</template>
<script>
import BurguerForm from '../components/BurguerForm.vue';
import Banner from '../components/Banner.vue';


export default {
  name:"Home",
  components: {
    Banner,
    BurguerForm,
  }
}
</script>

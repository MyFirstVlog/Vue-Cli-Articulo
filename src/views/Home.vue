<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <Titulo texto='Inicio de SPA'/>
  </div>
</template>

<script>
import Titulo from '../components/Titulo.vue'
// @ is an alias to /src


export default {
  name: 'Home',
  components: {
    Titulo
  }
}
</script>

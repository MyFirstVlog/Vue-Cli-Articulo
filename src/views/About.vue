<template>
  <div class="about">
    <img alt="Vue logo" src="../assets/logo.png">
    <Titulo texto="About Page"/>
  </div>
</template>


<script>
import Titulo from '../components/Titulo.vue'
// @ is an alias to /src

export default {
  name: 'About',
  components: {
    Titulo
  }
}
</script>
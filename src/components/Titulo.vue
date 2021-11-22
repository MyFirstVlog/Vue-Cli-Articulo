<template>
  <h1>{{texto}}</h1>
</template>

<script>
export default {
    props:{
        texto : String
    }
}
</script>

<style scoped>
    h1 {
        font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
        
    }
</style>
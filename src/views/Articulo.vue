<template>
  <Titulo texto="Route With Params"/>
  <h2>Articulo {{$route.params.id}}</h2> 
  <p>{{body}}</p>
</template>

<script>
import Titulo from '../components/Titulo.vue'
//Aqui recibo el params de id
export default {
    components:{
        Titulo
    },
    data() {
      return {
        body: ""
      }
    },
    methods:{
      async getBodyItem(){
        const id = this.$route.params.id
        console.log(id)
        const data = await fetch(`https://jsonplaceholder.typicode.com/posts/${id}`).then(res => res.json())
        const {body} = data
        this.body = body
      }
    },
    created(){
      this.getBodyItem()
    }
}
</script>

<style>

</style>
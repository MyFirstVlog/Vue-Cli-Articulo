<template>
<img alt="Vue logo" src="../assets/logo.png">
  <Titulo 
    texto='Titulo de Mi Blog'
  />
  <button @click="consumirApi">Consumir Api</button>
  
   <h5 v-for="(item, index) in arrayBlog" :key="index">
          {{item.id}}.<router-link :to="`/blog/${item.id}`">{{item.title}}</router-link>
    </h5>
  
</template>

<script>
import Titulo from '../components/Titulo.vue'

export default {
    components:{
        Titulo
    },
    data() {
        return {
            arrayBlog: []
        }
    },
    methods: {
        async consumirApi() {
            try {
                let data = await fetch('https://jsonplaceholder.typicode.com/posts').then(res => res.json())
                data = data.filter(each => each.id <= 10 )
                this.arrayBlog = data.map(each => {
                    return {
                        id : each.id,
                        title: each.title,
                        body : each.body
                    }
                })

            } catch (error) {
                console.log(error)
            }
        }
    },
    //es el ciclo de vida que se usa antes de que el template se ponga en la pag web
    created(){
        this.consumirApi()
    }

}
</script>

<style>
    router-link{
        text-decoration: none;
    }
</style>
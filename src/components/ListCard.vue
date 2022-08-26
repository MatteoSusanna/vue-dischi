<template>
  <div class="container">
    <MyCard v-for="musica in musicaArray" :key="musica.id" :oggetto="musica" />
  </div>
</template>

<script>
import axios from 'axios'
import MyCard from './MyCard'

export default {
    nome: 'ListCard',
    components:{
        MyCard
    },
    data(){
        return{
            musicaArray: []
        }
    },
    created(){
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then(musica =>{
            this.musicaArray = musica.data.response
        })
    }
}
</script>

<style lang="scss">


</style>
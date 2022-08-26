<template>
  <div class="container">
    <div class="wrapper-card">
        <MyCard v-for="(musica, indice) in musicaArray" :key="indice" :oggetto="musica" />
    </div>
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
    .wrapper-card{
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
    }
</style>
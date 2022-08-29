<template>
  <div class="container">
    <div class="wrapper-card">
        <MyCard v-for="(musica, indice) in musicaArray" :key="indice" :oggetto="musica" />
    </div>

    <select>
            <option v-for="(genere, indice) in filtraGeneri" :key="indice" value="" >{{genere.genre}}</option>
    </select>

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
    methods:{
        filtraGeneri(){
            const generiFiltrati = this.musicaArray.filter((generi =>{
                if(!generi.genre.includes()){
                    return true
                }else{
                    return false
                }
            }));
            return generiFiltrati
            
        }

    },
    created(){
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then(musica =>{
            this.musicaArray = musica.data.response;
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
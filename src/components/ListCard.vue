<template>
  <div class="container">
    <div class="wrapper-card">
        <MyCard v-for="(musica, indice) in stampaFiltrati" :key="indice" :oggetto="musica" />
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
    props:{
        generePassato: String
    },
    methods:{
        filtraGeneri(){

            let listaGeneri = [];

            this.musicaArray.forEach(album => {
                if(!listaGeneri.includes(album.genre)) {
                    listaGeneri.push(album.genre);
                }
            });
            return listaGeneri;            
        },

    },
    created(){
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then(musica =>{
            this.musicaArray = musica.data.response;

            let listaGeneri = [];

            this.musicaArray.forEach(album => {
                if(!listaGeneri.includes(album.genre)) {
                    listaGeneri.push(album.genre);
                }
            });

            this.$emit('popolaGeneri', listaGeneri);
        })
    },
    computed:{
        stampaFiltrati(){
            if(this.generePassato == null){
                return this.musicaArray;
            }else{
                const myValori = this.musicaArray.filter((musica =>{
                if(musica.genre.includes(this.generePassato)){
                    return true;
                }else{
                    return false;
                }
            }));
            return myValori;
            }
            
        }
    },
}
</script>

<style lang="scss">
    .wrapper-card{
        display: flex;
        flex-wrap: wrap;
    }
</style>
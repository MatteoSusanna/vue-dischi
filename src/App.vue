<template>
  <div id="app">

    <MyHeader @filtraGeneri="mioGenere" :mialista="newLista"/>

    <ListCard @popolaGeneri="setGeneri" :generePassato="generi"/>

  </div>
</template>

<script>
import ListCard from './components/ListCard'
import MyHeader from './components/MyHeader'

export default {
  name: 'App',
  components: {
    ListCard,
    MyHeader
  },
  data(){
    return{
      newLista: null,
      generi: null,
    }
  },
  methods: {
    setGeneri(listaGeneri) {
        this.newLista = listaGeneri
    },

    mioGenere(mioGenere){
      this.generi = mioGenere;
    }
  }
}
</script>

<style lang="scss">
  @import '@/styles/general.scss';


</style>

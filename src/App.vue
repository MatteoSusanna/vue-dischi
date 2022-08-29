<template>
  <div id="app">

    <MyHeader :mialista="newLista" />

    <ListCard @popolaGeneri="setGeneri"/>

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
    }
  },
  methods: {
    setGeneri(listaGeneri) {
        this.newLista = listaGeneri
    }
  }
}
</script>

<style lang="scss">
  @import '@/styles/general.scss';


</style>

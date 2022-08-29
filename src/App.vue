<template>
  <div id="app">

    <MyHeader />

    <ListCard />

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
  }
}
</script>

<style lang="scss">
  @import '@/styles/general.scss';


</style>

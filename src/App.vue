<template>
  <div id="app">

    <ListCard />

  </div>
</template>

<script>
import ListCard from './components/ListCard'

export default {
  name: 'App',
  components: {
    ListCard
  }
}
</script>

<style lang="scss">
  @import '@/styles/general.scss';


</style>

<template>
    <div class="card">
        <div class="img">
            <img :src="oggetto.poster">
        </div>
        <h3>{{oggetto.title}}</h3>
        <div>{{oggetto.author}}</div>
        <div>{{oggetto.year}}</div>
    </div>
</template>

<script>

export default {
    nome: 'MyCard',
    props:{
        oggetto: Object
    }
}
</script>

<style lang="scss">

    .card{
        width: calc(100% / 5 - 1rem);
        img{
            width: 100%;
        }
    }


</style>
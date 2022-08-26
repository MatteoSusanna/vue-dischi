<template>
    <div class="card">
        <div class="img">
            <img :src="oggetto.poster">
        </div>
        <h3>{{oggetto.title}}</h3>
        <div class="text">{{oggetto.author}}</div>
        <div class="text">{{oggetto.year}}</div>
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
    @import '@/styles/var.scss';

    .card{
        width: calc(100% / 5 - 1rem);
        margin-bottom: 1rem;
        padding: 15px;
        background-color: $card_background;
        .img{
            width: 100%;
            height: 200px;
            object-fit: cover;
            img{
                width: 100%;
                height: 100%;
            }
        }
        h3{
                color: $text_primary;
                text-align: center;
        }
        .text{
            text-align: center;
            color: $text_secondary;
        }
        
    }


</style>
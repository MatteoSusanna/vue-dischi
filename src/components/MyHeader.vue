<template>
    <header>
        <select>
            <option v-for="(genere, indice) in mialista" 
            :key="indice" 
            :value="genere"
            @change="selezione">
            {{genere}}</option>
        </select>


    </header>
</template>

<script>
export default {
    nome: 'MyHeader',
    props:{
        mialista: Array
    }

}
</script>

<style lang="scss">
    header{
        height: 100px;
        display: flex;
        justify-content: center;
        align-items: center;
    }
</style>
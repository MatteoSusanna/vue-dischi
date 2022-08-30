<template>
    <header>
        <select @change="selezione($event)">
            <option value="">Seleziona genere</option>
            <option v-for="(genere, indice) in mialista" 
            :key="indice" 
            :value="genere">
            {{genere}}</option>
        </select>


    </header>
</template>

<script>
export default {
    nome: 'MyHeader',
    props:{
        mialista: Array,
    },
    data(){
        return{
            datofiltrato: null,
        }
    },
    methods:{
        selezione(event){
            this.datofiltrato = event.target.value;
            this.$emit('filtraGeneri', this.datofiltrato);
        }
    },
    created(){
        this.$emit('filtraGeneri', this.datofiltrato);
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
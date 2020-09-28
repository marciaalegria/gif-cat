<template>
<div>
    
    <h1>Random Gif Cat</h1>
    <form action="">

        <label for="">Título</label>
        <input type="text" v-model="gatitos.titulo">
        <label for="">Filtro</label>
        <select name="" id=""></select>    
        <label for="">Color</label>
        <select name="" id=""></select>
        <label for="">Tamaño</label>
        <input type="text">
        <input type="submit" value="Obtener mi gatito" @click.prevent="fetchCharacter">
    </form>
</div>
</template>

<script>
export default {
    name: 'hijo-component',
    // props: {},
    data: function(){
        return {
            gatitos: {
                titulo:'',
                filtro:'',
                color:'',
                tamaño:'',
            }
        }
    },
    computed: {
        image(){
            return this.gatitos.image;
        }
    },
    methods: {
        fetchCharacter(){
            //fetch(`https://cataas.com/cat/gif/says/${this.gatitos.titulo}?filter=${this.gatitos.filtro}&color=${this.gatitos.color}&size=${this.gatitos.tamaño}&type=or`)
            fetch(`https://cataas.com/cat/gif/says/holi?filter=sepia&color=orange&size=40&type=or`)
            .then(response => response.json())
            .then(json => {
                console.log(json)
                this.addCharacter(json);
            })
            .catch(error => {
                console.log(error)
            })
        },
        addCharacter(json){
            if(json.results[0] === undefined){
                alert('no ta');
                return;
            }
            this.gatitos = json.results[0];
        }
    },
    // components: {},
}
</script>

<style scoped>
    
</style>
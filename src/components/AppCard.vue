<script>
export default{
    data(){
        return{

        }
    },
    props:{
        immagine: String,
        nome: String,
        tipo: String,
    }
}
</script>
<template>
    <div class="card-container">
        <img :src="immagine" alt="carta">
        <div>NOME: {{ nome }}</div>
        <div>TIPO: {{ tipo }}</div>
    </div>
</template>
<style lang="scss" scoped>
 .card-container {
    width:calc(100% / 5 - 30px / 5 * 4);
    img{
        width: 100%;
    }
 }
</style>
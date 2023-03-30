<script>
import { store } from '../store';
export default{
    name: "AppSearch",
    data(){
        return{
        store,
    }
    }
}
</script>
<template>
    <label for="nome-carta">Cerca carte per nome:  </label>
    <input id="nome-carta" type="text" v-model="this.store.inp">
    <button @click="$emit('clickButton')">OK</button>
</template>
<style lang="scss" scoped>

label{
    margin-left:200px;
}

button{cursor: pointer;}
</style>
<script>
import { store } from './store';
import axios from "axios";
import AppMain from './components/AppMain.vue';
import AppHeader from './components/AppHeader.vue';

export default{
  data(){
    return{
      store,
    }
  },
  created(){
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=50&offset=0') .then ((res)=>{
      console.log(res.data.data);
      this.store.cards = res.data.data;
    });
  },
  components:{
    AppMain,
    AppHeader
  }
}
</script>

<template>

  <AppHeader></AppHeader>
  <AppMain></AppMain>

</template>

<style scoped>
</style>

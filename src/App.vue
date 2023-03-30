<script>
import { store } from './store';
import axios from "axios";
import AppMain from './components/AppMain.vue';
import AppHeader from './components/AppHeader.vue';
import AppSearch from './components/AppSearch.vue';

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
    AppHeader,
    AppSearch
  },
  methods:{
        mostraCarte(){
              axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=50&offset=0&fname='+this.store.inp).then((response) => {
        this.store.cards = response.data.data;
            })
    }
}
}
</script>

<template>

  <AppHeader></AppHeader>
  <AppSearch @clickButton="mostraCarte()"></AppSearch>
  <AppMain></AppMain>

</template>

<style scoped>
</style>

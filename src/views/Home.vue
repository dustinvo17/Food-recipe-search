<template>
  <div class="home">
    <SearchBar v-on:search="handleSearch"/>
    <ItemList v-bind:items="this.items"/>
  </div>
</template>

<script>
import axios from 'axios'
// @ is an alias to /src
import ItemList from '../components/ItemList'
import SearchBar from '../components/SearchBar.vue'

export default {
  name: 'home',
  components: {
    SearchBar,
    ItemList
  },
  created() {
 
  },
  data(){
    return {
      items:[]
    }
  },
  methods:{
    handleSearch(itemToSearch){
      axios.get('https://api.edamam.com/search',{
        params: {
           q:itemToSearch,
          app_id:'63622b12',
          app_key:'582f9b15274516eb32c4014e2e1d76ff'
        }
       
      }).then(res => this.items = res.data.hits)
      
    }
  }
}
</script>

<template>
    <div>
      <form @submit="()=>this.$emit('search',this.food)">
      <input v-model="food" type="text">
      <input type="submit" value="Search">
      <p>{{this.food}} list recipe</p>
    
  </form>
</div>

</template>

<script>
export default {
    name:'SearchBar',
    data(){
        return {
            food:''
        }
    }
}
</script>

<style>

</style>
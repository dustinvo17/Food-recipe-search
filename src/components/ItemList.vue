<template>
    <div>
        <div  class="container">
            <div class="item"  v-for="item in items" :key="item.recipe.uri">
                <img v-bind:src="item.recipe.image" >
                <p>{{item.recipe.label}}</p>
                <p>Calories {{item.recipe.calories}}</p>
                
                <ul>
                    <li v-for="(spice,index) in item.recipe.ingredientLines" v-bind:key="index" >
                        {{spice}}
                      
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name:"ItemList",
    props:["items"],
   
}
</script>

<style>
.container {
    width:80%;
    margin:0 auto;
    display:grid;
    grid-template-columns: repeat(2,1fr);
    grid-gap:20px;

}
.item {
    border:1px solid gray;
}
li {
    list-style: none;
    line-height:2;
}
</style>
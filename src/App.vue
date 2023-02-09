<template>
<div class="container">
  <GroceryList/>
</div>
</template>

<script>
import GroceryList from './components/GroceryList.vue'

export default {
  name: 'App',
  components: {
    GroceryList
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Lobster&display=swap');

*{
padding: 0;
margin: 0;
}

body{
font-family: 'Lobster', cursive;
}

.container{
width: 90%;
margin: auto;
display: flex;
justify-content: center;
align-items: center;
}

</style>

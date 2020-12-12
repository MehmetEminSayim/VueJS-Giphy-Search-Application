<template>
  <div class="container">
    <ul class="">
      <li class="text-center" v-for="item in gifs">
        <img  :src="item.images.fixed_height.url" alt="">
      </li>
    </ul>
  </div>

</template>

<script>
  export default {
    props : ['gifs'],
    created() {
      
    }
  }
</script>

<style scoped>
 li{
   list-style: none;
   float: left;
   margin:20px ;
 }
</style>

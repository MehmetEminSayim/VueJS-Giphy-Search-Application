<template>
  <div class="container ">
    <div class="row">
      <div class="col-md-3"></div>
      <div class="col-md-6">
        <div class="card mt-5 p-2 ">
          <div class="card-header">
            <h4 class="text-center">Giphy Mağazaya Hoşgeldiniz</h4>
          </div>
          <div class="form-group">
            <input type="text" v-model="query" class="form-control" @keypress.enter="gipSearch" placeholder="Gifs Ara...">
          </div>
          <br>
          <div class="text-right">
            <button @click="gipSearch" class="btn btn-primary">Arama </button>
          </div>
        </div>
      </div>
      <div class="col-md-3"></div>
    </div>
  </div>
</template>

<script>
  export default {
    data(){
      return {
        query : ""
      }
    },
    methods : {
      gipSearch(){
        this.$emit("searchResult" , this.query);
      }
    }
  }
</script>

<style scoped>

</style>

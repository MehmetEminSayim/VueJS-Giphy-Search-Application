<template>
  <div class="containder">
    <p v-if="isLoading">Loading...</p>
    <div class="">
      <app-search v-on:searchResult = "searchRes" ></app-search>
      <app-preview :gifs=gifs></app-preview>
    </div>
  </div>
</template>

<script>
import Search from "./components/Search";
import Preview from "./components/Preview";
export default {
  components : {
    appSearch : Search,
    appPreview : Preview
  },
  data(){
    return {
      gifs : [],
      isLoading :true
    }
  },
  methods: {
    searchRes(query){
      this.gifs = [];
      this.isLoading = true;
      fetch(`http://api.giphy.com/v1/gifs/search?q=${query}&api_key=D1WIHGFRLpcT6UFD6StYHP6dfWTKoO6l`)
        .then(response => {
          return response.json()
        })
        .then(response => {
          console.log(response)
          this.gifs = response.data
          this.isLoading = false
        })
    }
  },
  created() {
    fetch("http://api.giphy.com/v1/stickers/trending?api_key=D1WIHGFRLpcT6UFD6StYHP6dfWTKoO6l")
      .then(response => {
        return response.json()
      })
    .then(response => {
      console.log(response)
      this.gifs = response.data
      this.isLoading = false
    })
  }
}
</script>
<style>

</style>

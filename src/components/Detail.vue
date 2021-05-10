<template>
  <div>
      <h1>movie detail</h1>
      <p>{{detailObj.title}}</p>
  </div>
</template>

<script>
import axios from 'axios'
export default {
    name: "Detail",
    data(){
        return{
            id:this.$route.params.id,
            detailObj: {}
        }
    },
    mounted(){
        axios.get(`https://api.themoviedb.org/3/movie/${this.id}?api_key=8aca17faf6bf476ec035b28e2de1f418&language=en-US`)
        .then(response => {
            console.log(response);
            this.detailObj = response.data
            

        })
    }
}
</script>

<style>

</style>
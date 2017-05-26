<template lang="html">
   <div class="col-md-9">
      <div class="col-md-12">
         <div class="row">
            <div class="col-md-3" v-for="(popular, index) in myPopular.results" v-if="index <20">

               <div class="my-image">
                  <!-- {{popular.title}} -->
                  <img :src="'https://image.tmdb.org/t/p/w640/' + popular.poster_path" alt="" class="img-responsive">
                  <div class="background-title">
                     <h3 class="movie-title">{{popular.title}}</h3>
                  </div>
               </div>

            </div>
         </div>
      </div>
   </div>

</template>

<script>
export default {
   data() {
      return {
         myPopular: '',
      }
   },
   methods : {
      getPopular() {
         fetch('https://api.themoviedb.org/3/movie/popular?api_key=4bd3b71ae20e0bccb619c9d3a71ee33a&language=en-US&page=1', {
            method: 'GET'
         })
            .then(response => response.json())
            .then(json => this.myPopular = json);
      }
   },
   created() {
      this.getPopular()
   }
}
</script>

<style lang="css">
   .my-image{
      margin: 5px;
      position: relative;
      overflow: hidden;
      border: 1px solid #999;
      border-radius: 4px;
   }

   .background-title {
      background: #000;
      padding: 0 5px;
      opacity: 0.9;
      position: absolute;
      bottom: 0;
      width: 100%;
      border-bottom-left-radius: 4px;
      border-bottom-right-radius: 4px;
   }

   .my-image img{
      border: none;
      border-radius: 5px;
   }

   .movie-title {
      font-size: 13px;
      font-weight: bold;
      color: #fff;
      margin: 7% 0;
      display: inline-block;
      width: 100%;
      text-align: center;
   }

</style>

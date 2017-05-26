<template lang="html">
   <div class="col-md-3 my-sidebar">
      <div class="col-md-12 my-sidebar">
         <div class="sidebar-title">
            <h2>Popular Series Now</h2>
         </div>
         <div
            class="sidebar-popular-title"
            v-for="(popular, index) in popularSidebar.results"
            v-if="index < 5">
               <div class="row border-bottom">
                  <div class="col-md-3 img-sidebar-popular">
                     <img
                     :src="'https://image.tmdb.org/t/p/w640/' + popular.poster_path"
                     class="img-responsive img-sidebar-border">
                  </div>
                  <div class="col-md-8 desc-sidebar-popular">
                     <span class="pull-right sort-popular badge">
                        <i># {{index+1}}</i>
                     </span>
                     <p class="title-sidebar-popular text-left">
                           {{ popular.title }}
                     </p>
                     <p><strong class="label label-primary sidebar-label">Popular</strong> : <i>{{ popular.popularity }}</i></p>
                     <p><strong class="label label-success sidebar-label">Score</strong> : <i>{{ popular.vote_average }}</i></p>
                     <p><strong  class="label label-warning sidebar-label">Total Vote</strong> : <i>{{ popular.vote_count}}</i></p>
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
         popularSidebar : '',
         popularCount: 1
      }
   },
   methods : {
      getPopularSidebar() {
         fetch('https://api.themoviedb.org/3/movie/popular?api_key=4bd3b71ae20e0bccb619c9d3a71ee33a&language=en-US&page=1', {
            method: 'GET'
         })
            .then(response => response.json())
            .then(json => this.popularSidebar = json);
      }
   },
   created() {
      this.getPopularSidebar()
   }
}
</script>

<style lang="css">
   .my-sidebar{
      padding: 0;
      border-right: 1px solid #aaa;
   }

   .sidebar-title {
      background: #077fd5;
      padding: 5px;
      margin: 5px
   }

   .sidebar-title h2{
      font-size: 16px;
      font-weight: bold;
      margin: 0px;
      padding: 5px;
      color: #fff;
   }

   .border-bottom {
      border-bottom: 1px solid #ddd;
   }

   .sidebar-label {
      font-size: 10px;
   }

   .sidebar-popular-title {
      margin: 5px;
      overflow: hidden;
      white-space: nowrap;
      text-overflow: ellipsis;
   }

   .img-sidebar-border {
      border: 1px solid #ccc;
      border-radius: 3px;
   }

   .img-sidebar-popular {
      margin-bottom: 5px;
      margin-right: 0;
      padding-right: 8px;
   }

   .desc-sidebar-popular {
      color: #fff;
      padding: 0;
      font-size: 11px;
      line-height: 0.7
   }

   .title-sidebar-popular {
      padding: 5px 0;
      color: #fff;
      font-size: 13px;
      font-weight: bold;
      border-bottom: 1px solid #ddd;
   }

   .sort-popular {
      font-size: 11px;
      font-weight: bold;
      position: relative;
   }
</style>

<template lang="html">
   <div class="my-body">
      <Navbar />

      <div class="container content-background">
         <Sidebar />
         <MyContent />
      </div>
   </div>

</template>

<script>
import Navbar from './components/Navbar.vue'
import Sidebar from './components/Sidebar.vue'
import MyContent from './components/MyContent.vue'

export default {
   data() {
      return {

      }
   },
   components : {
      Navbar, Sidebar, MyContent
   }
}
</script>

<style lang="css">
   .my-body {
      background: url(https://image.tmdb.org/t/p/original/24GSBmRoQlX7tnHvH5BTPq2eMVQ.jpg) no-repeat center center fixed;
     -webkit-background-size: cover;
     -moz-background-size: cover;
     -o-background-size: cover;
     background-size: cover;
   }

   .content-background {
      background-color: #000;
      /*border: 1px solid #eee;*/
      padding: 15px;
      border-radius: 5px;
      opacity: .9
   }

</style>

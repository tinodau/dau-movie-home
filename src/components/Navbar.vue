<template lang="html">
   <nav class="navbar navbar-inverse navbar-square">
     <div class="container">
       <!-- Brand and toggle get grouped for better mobile display -->
       <div class="navbar-header">
         <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#bs-example-navbar-collapse-1" aria-expanded="false">
           <span class="sr-only">Toggle navigation</span>
           <span class="icon-bar"></span>
           <span class="icon-bar"></span>
           <span class="icon-bar"></span>
         </button>
         <a class="navbar-brand my-navbar-title" href="#"><i>Dau Movies</i></a>
       </div>

       <!-- Collect the nav links, forms, and other content for toggling -->
       <div class="collapse navbar-collapse" id="bs-example-navbar-collapse-1">
         <ul class="nav navbar-nav navbar-right navbar-menu">
            <li><a href="#">Popular</a></li>
            <li><a href="#">Latest</a></li>
            <li><a href="#">Playing</a></li>
            <li><a href="#">Upcoming</a></li>
            <form class="navbar-form navbar-left">
               <div class="form-group">
                  <input type="text" class="form-control navbar-search" placeholder="Search...">
               </div>
            </form>
         </ul>
       </div><!-- /.navbar-collapse -->
     </div><!-- /.container-fluid -->
   </nav>
</template>

<script>
export default {
}
</script>

<style lang="css">
.navbar-square {
   border-radius: 0;
   opacity: 0.8;
   background: #000;
}

.navbar-menu li a{
   font-weight: bold;
   color: #fff !important;
}

.navbar-search {
   border-radius: 0;
}

.navbar-search::-webkit-input-placeholder {
color: #333 !important;
}

.navbar-search:-moz-placeholder { /* Firefox 18- */
color: #333 !important;
}

.navbar-search::-moz-placeholder {  /* Firefox 19+ */
color: #333 !important;
}

.navbar-search:-ms-input-placeholder {
color: #333 !important;
}

.my-navbar-title {
   font-weight: bold;
   color: #fff !important;
}

</style>

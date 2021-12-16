<template>
    <section class="card">
        <div class="card-content">
            "{{card.moviename1}}" <!--Most of the information is set up in App.vue Whatever the current card is, we are essentially having that be the content for our div-->   
            <img v-bind:src="'http://image.tmdb.org/t/p/w500/' + card.poster_path1" width='100px'><!--Image will be concatanated with the poster path-->
        </div>
        <div class="card-info">
            <div class="card-author">
                -{{card.overview1}}  <!--most of the stuff is already linked from app.vue and all we have to do is use card to get to our author name-->
                
            </div>
        </div>
        <div class="card-content">
            "{{card.moviename2}}" <!--Most of the information is set up in App.vue Whatever the current card is, we are essentially having that be the content for our div--> 
            <img v-bind:src="'http://image.tmdb.org/t/p/w500/' + card.poster_path2" width='100px'><!--Image will be concatanated with the poster path-->

        </div>
        <div class="card-info">
            <div class="card-author">
                -{{card.overview2}}  <!--most of the stuff is already linked from app.vue and all we have to do is use card to get to our author name-->
            </div>
        </div>
        <div class="card-content">
            "{{card.moviename3}}" <!--Most of the information is set up in App.vue Whatever the current card is, we are essentially having that be the content for our div--> 
            <img v-bind:src="'http://image.tmdb.org/t/p/w500/' + card.poster_path3" width='100px'><!--Image will be concatanated with the poster path-->

        </div>
        <div class="card-info">
            <div class="card-author">
                -{{card.overview3}}  <!--most of the stuff is already linked from app.vue and all we have to do is use card to get to our author name-->
                
            </div>
        </div>
        <div class="card-content">
            "{{card.moviename4}}" <!--Most of the information is set up in App.vue Whatever the current card is, we are essentially having that be the content for our div--> 
            <img v-bind:src="'http://image.tmdb.org/t/p/w500/' + card.poster_path4" width='100px'> <!--Image will be concatanated with the poster path-->

        </div>
        <div class="card-info">
            <div class="card-author">
                -{{card.overview4}}  <!--most of the stuff is already linked from app.vue and all we have to do is use quote to get to our author name-->
            </div>
        </div>
              
       
    </section>
</template>

<script>
export default {
    props: ['card']
}
</script>

<style scoped> /*Scoped feature is something I learned more through this fiasco that has helped with styling in vue. style specific parts */


    .card{
        display:flex;
        align-items:flex-end;
        border:5px solid red;

    }

    .card-author{
        flex:33.33%;
        padding: 15px;
        border:5px solid red;

    }

   


</style>
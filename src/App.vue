<!--Author: Victor M-->


<template> 
  <div id="app">
    <Header title="Popular Tv Shows"/> <!--This will change the quote-->
    <Card :card="card"/> <!--Display Card-->


  



  </div>
</template>

<script>
import Header from './components/Header.vue'; //we will import required information by using 'import' and telling it where out component is being kept
import Card from './components/Card.vue';
import axios from 'axios'

export default {
  name: 'App', 
  components: { //all the compoents nesecarry will be listed here
      Header, //for the title
      Card, //for the quote box
    },

    data() {
      return{ 
        card: { 
          moviename1: 'Blank', //what ever is here is a place holder as soon as page loades this will be replaced
          moviename2:'Blank',
          moviename3:'Blank',
          moviename4:'Blank',

          overview1: 'Blank', //place holder for the overview that will then be replaced once information is found
          overview2: 'Blank',
          overview3: 'Blank',
          overview4: 'Blank',

          poster_path1: 'blank',
          poster_path2: 'blank',
          poster_path3: 'blank',
          poster_path4: 'blank',

        },
      }
    },

    mounted() 
    {
      axios.get(`https://api.themoviedb.org/3/tv/popular?api_key=bbc40296e39709a06219deffc4574568&language=en-US&page=1`) //the api that we will be using to the most popular movies
      .then( (response) =>{

        console.log(response)
        console.log(response.data.results[0].poster_path)


        this.card ={ //we will take the responses that we are giving and parse through for specific information. When we get just the response, it is extra information that we don't need. 
          moviename1: response.data.results[0].name, 
          overview1: response.data.results[0].overview,
          poster_path1: response.data.results[0].poster_path,

          moviename2: response.data.results[1].name,
          poster_path2: response.data.results[1].poster_path,
          overview2: response.data.results[1].overview,

          moviename3: response.data.results[2].name,
          poster_path3: response.data.results[2].poster_path,
          overview3: response.data.results[2].overview,

          moviename4: response.data.results[3].name,
          poster_path14: response.data.results[3].poster_path,

          overview4: response.data.results[3].overview
        }
      })
    }
  
}
</script>

<style> 

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif; /*This is styling for the page */
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;  /*constant*/
  margin-top: 60px;
} 


.button-cover{ /*This is to style the button that will be used to click to the next quote */
  display:flex;
  padding:0;
  justify-content:center;
  margin: 64px auto;
}

button {
  border: none;
  border: none;
	outline: none;
	background-color:blueviolet;
	padding: 16px 32px;
	border-radius: 99px;
}
</style>

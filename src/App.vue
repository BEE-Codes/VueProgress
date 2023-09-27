<template>
  <div>
    <h2>Volume Tracker (0-20)</h2>
    <h3>Current Volume {{ volume }}</h3>
    <div>
      <button @click="volume += 2">Increase</button>
      <button @click="volume -= 2"> Decrease</button>
    </div>

    <input type="text" v-model="movie">
    <input type="text" v-model="movieInfo.Title">
    <input type="text" v-model="movieInfo.Cast">
    
    <div>
      <button @click="movieList .push('wonder woman')"> Add movie </button>
      <!-- may be used without the deep property on the script watcher -->
      <button @click="movieList = movieList.concat(['wonder woman'])"> Add movie</button>
    </div>
    <welcomeItem />
    <todo/>
    <forms/>
    <components/>
    <!-- reusing components  -->
    <!-- component props{props are custom attributes you can register on the component which allows the component content to be dynamic} 
    to specify props for a coponent,you add custom attributes-->


    <components name="Michelle" thing="girl"/>
    <components name="Marcus" thing="bot"/>
    <!-- using v-bind directive on component -->
    <components :name="name" :thing="learning"/> 
    <Article/>  
    <Article title="Article Title" :likes="50" :IsPublished="Yes"/> 
    <button @click="pop()">{{btnContent}}</button>
    <ComponentEvents v-if="ShowPopup == true"/>

      <!-- using v-model directives on components -->

    <label for="input"> Name</label>
    <input type="text" v-model="initials">

    <!-- slots are like props but they allow the parent component to control the content of the child component including html elements-->
    <!-- DON'T GIVE UP, YOU'RE ALMOST THERE -->
    
    <card>Card Content </card>
    <card> <h2> Card Content </h2> </card>
    <card> <img src="https://picsum.photos/200" alt=""> </card>
  </div>
</template>


<script>
import WelcomeItem from './components/WelcomeItem.vue'
import todo from './components/todo.vue'
import forms from './components/forms.vue'
import Components from './components/Components.vue'
import Article from './components/Article.vue'
import ComponentEvents from './components/ComponentEvents.vue'
import card from './components/card.vue'

export default {
  name: 'App',
  components:{
    WelcomeItem,
    todo,
    forms,
    Components,
    Article,
    ComponentEvents,
    card,
  },
  data (){
    return {
      volume: 0,
      movie: "",
      movieInfo:{
        Title:"",
        Cast:""
      },
      movieList:['The flash','Superman'],
      ShowPopup: false,
      btnContent: 'show',
      initials:'',
    }
  },
  methods: {
    pop(){
      this.ShowPopup = !this.ShowPopup;
      if(this.ShowPopup == true){
        this.btnContent = 'Close'
      }  else {
        this.btnContent = 'show';
      }
    }
  },
  // Brightt() {
  //   return {
  //     name:'Bright',
  //     learning: 'VueJs'
  //   }
  // },

  watch: {
    volume(newVolume,oldVolume){
      if (newVolume > oldVolume && newVolume === 16 ){
        alert ("Volume above 16 may cause damage to your hearing")
      }
    },
    movie:{
      handler (newMovie){
        console.log(` calling API with movie name = ${newMovie}`)
      },
      // runs a watcher on page load
      immediate: true, 
    },
    movieInfo: {
      handler(newMovie) {
        console.log(` calling API with movie title= ${newMovie.Title} and actor =${newMovie.Cast}`)
      },
      // enables vue to watch deeply nested properties
      deep: true,
    } ,
      movieList: {
      handler(newMovie) {
        console.log(` calling API with movie list = ${newMovie}`)
      },
      // runs a watcher on page load
      deep: true,
    },
    
  }
}
</script>


<style>

</style>
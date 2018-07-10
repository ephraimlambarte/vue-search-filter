<template>
  <div id="app" class='container'>
    <!-- <img src="./assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <!-- <h1>Hello 
      
      <template v-if="gender=='male'">Mr.</template>
      <template v-if="gender=='female'">Ms.</template>
      {{name}}
    </h1>
    <label>Enter your gender:</label>
    <input type = 'text' v-model= "gender" class='form-control'>
    <label>Enter your name:</label>
    <input type = 'text' v-model= "name" class='form-control'> -->
   
   <h1>List Of Stories</h1>
   <ul class="list-group">
      <li v-for="(story, index) in filtered" class="list-group-item">
        {{index + 1}} .) {{story.title}} by {{story.writer}}
      </li>
      <!-- <li v-for = "value in storyObj" class= "list-group-item">
        {{$key}} {{$index}} {{value}}  
      </li> -->
   </ul>
   <label for = "query">Search for a movie: </label>
   <input type = 'text' v-model="query" >
  </div>
</template> 

<script>

import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'app',
  data(){
    return {
      query:"",
      name:"",
      gender:"",
      stories:[
        {title:"The quick brown fox",
        writer:"Edgar Allan Po"},
        {title:"Little Red Riding Hood",
        writer: "Ephraim R. Lambarte"},
        {title:"Humpty dumpty jumped",
        writer:"Antoine Tagadaya"},
        {title:"Cinderella",
        writer:"Benjie Yabut"}
      ],
      storyObj:{
        title:"Huntsman",
        writer:"John Doe",
        produce:"Piolo"
      }
    }
  },
  computed:{
    filtered:function(){
      if(this.query == ""){
        return this.stories;
      }else{
        return this.stories.filter(obj => {
          return obj.title.includes(this.query);
        });
      }
    }
  },
  components: {
    HelloWorld
  }
}
</script>

<style>

input {
  width:100%;
  height:25px;
}
</style>

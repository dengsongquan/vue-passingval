<template>
  <hello-world :todos="todos">
    <template slot-scope="slotProps">
      <span v-if="slotProps.todo.isComplete"></span>
      <span>{{slotProps.todo.text}}</span>
    </template>
  </hello-world>
  <hello-world :msg="msg" v-model="msg" />

</template>

<script>

import HelloWorld from "./components/HelloWorld";
export default {
  name: 'App',
  components: {
      HelloWorld
  },
    data(){
      return{
          msg:'',
         todos:[
             {
                 id:0,
                 text:'raily0',
                 isComplete: false
             },
             {
                 text:'raily01',
                 id:1,
                 isComplete: true
             },
             {
                 text:'raily02',
                 id:2,
                 isComplete: false
             },
             {
                 text:'raily03',
                 id:3,
                 isComplete: false
             }
         ]
      }
    },
    methods:{
    }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

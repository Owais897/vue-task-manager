<template>
<div class="container">
  <Header title="Task Tracker"></Header>
  <Tasks  @toggle-reminder="toggleReminder"  @delete-task="deleteTask" :tasks="tasks"/>
</div>
</template>

<script>

import Header from "./components/Header.vue"
import Tasks from "./components/Tasks.vue"
export default {
  name: 'App',
  components: {
  Header,
  Tasks
  },
  data(){
    return {
      tasks :[]
    }
  },
  methods:{
    deleteTask(id){
      if(confirm("are you sure?")){
        this.tasks=this.tasks.filter(v=>v.id!=id)
      }
      console.log('id llllllllllll: ', id);

    },
    toggleReminder(id){
      console.log('id: ttttttttttt ', id);

    }
  },
  created(){
    this.tasks = [
      {
        id:45,
        text:"123",
        day : "mon",
        reminder:true
      },
        {
        id:32,
        text:"43",
        day : "tue",
        reminder:true
      },  {
        id:12,
        text:"34242",
        day : "wed",
        reminder:false
      },
    ]
  }
}
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: 'Poppins', sans-serif;
}
.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid steelblue;
  padding: 30px;
  border-radius: 5px;
}
.btn {
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}
.btn:focus {
  outline: none;
}
.btn:active {
  transform: scale(0.98);
}
.btn-block {
  display: block;
  width: 100%;
}
</style>

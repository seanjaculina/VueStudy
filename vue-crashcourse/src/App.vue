<template>
  <div class="container">
   <Header title="Task Tracker"/>
   <Tasks :tasks="tasks"/>
   
    </div>

</template>

<script>
import Header from './components/Header.vue'
import Tasks from './components/Tasks.vue'
import Testing from './components/Testing.vue'
export default {
  name: 'App',
  components:{
    Header, 
    Tasks,
    Testing

  },
  data(){
    return {
      tasks: []
    }
  },
  created(){
    this.tasks = [{
      id: 1,
      text: "Dr Appointment",
      day: "March 20th at 2:30PM",
      reminder: true,
    },
    {
      id: 2,
      text: "Birthday Celebration",
      day: "March 23rd at 12:00AM",
      reminder: true,
    },
    {
      id: 3,
      text: "Grocery Shopping",
      day: "March 24th at 5:30PM",
      reminder: true,
    },
    ]
  }

}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: 'Poppins', sans-serif;
  background-color: grey
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

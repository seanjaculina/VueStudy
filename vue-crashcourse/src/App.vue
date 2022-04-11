<template>
  <div class="container">
   <Header title="Task Tracker"/>
   <Tasks @toggle-reminder="toggleReminder" @delete-task="deleteTask" :tasks="tasks"/>

    </div>

</template>

<script>
import Header from './components/Header.vue'
import Tasks from './components/Tasks.vue'

export default {
  name: 'App',
  components:{
    Header, 
    Tasks,


  },
  data(){
    return {
      tasks: []
    }
  },
  methods:{
    deleteTask(id){
      if(confirm('Are you sure you want to delete this task?')){
        this.tasks = this.tasks.filter((task) => task.id !== id)
      }
    },
    // changing the color for task reminders, if the task id is equal to the id of the element that is clicked on the page, change it to the opposite (!task.reminder)
    toggleReminder(id){
      this.tasks = this.tasks.map((task) => task.id === id ? {...task, reminder: !task.reminder} : task )
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
      reminder: false,
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

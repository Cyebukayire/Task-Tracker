<template>
  <div class="container">
    <Header @toggle-add-task="toggleAddTask" title="Task Tracker"/>
    <div v-show="showAddTask">
    <AddTask @add-task="addTask" />
    </div>
    <Tasks @toggle-reminder="toggleReminder" @delete-task="deleteTask" :tasks="tasks"/>
  </div>
</template>

<script>
import Header from './components/Header'
import Tasks from './components/Tasks'
import AddTask from './components/AddTask'

export default {
  name: 'App',
  components: {
    Header,
    Tasks,
    AddTask
  },

  data(){
    return {
      tasks: [],
      showAddTask: false
    }
  },

  methods: {

    addTask(task) {
      this.tasks = [...this.tasks, task]
    },

    toggleAddTask(task) {
      this.showAddTask = !this.showAddTask
    },

    deleteTask(id) {
      if(confirm('Are you sure?')) {
      this.tasks = this.tasks.filter((task) => task.id !== id)
      }
    },
     
    toggleReminder(id) {
      this.tasks = this.tasks.map((task) => task.id === id ?
        { ...task, reminder: !task.reminder } : task)
    },
  },

  created() {
    this.tasks = [
      {
        id: 1,
        text: 'Doctors Appointment',
        day: 'March 1st at 2:30 pm',
        reminder: true,
      },
      {
        id: 2,
        text: 'Project Meeting',
        day: 'March 1st at 3:30 pm',
        reminder: true,
      },
      {
        id: 3,
        text: 'IELTS Exams',
        day: 'March 1st at 5:30 pm',
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

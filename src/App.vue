<template>
  <div class="container">
    <HeaderDeneme :showForm="showTodo" @toggleForm="toggleForm($event)" title="Todo List" />
    <div v-if="showTodo">
      <TaskForm @addTodo="addTodo($event)" />
    </div>
    <TasksA @deleteTask="deleteTask($event)" :tasks="tasks" />
  </div>
</template>

<script>
import HeaderDeneme from "./components/Header.vue";
import TasksA from "./components/Tasks.vue";
import TaskForm from "./components/TaskForm.vue";

export default {
  name: "App",
  components: {
    HeaderDeneme,
    TasksA,
    TaskForm
},
  created() {
    this.tasks = [
      {
        _id: 1,
        text: "React",
        day: "Monday",
      },
      {
        _id: 2,
        text: "Vue",
        day: "Monday",
      },
      {
        _id: 3,
        text: "Angular",
        day: "Monday",
      },
      {
        _id: 4,
        text: "Svelte",
        day: "Monday",
      },
    ];
  },
  data() {
    return {
      tasks: [],
      showTodo:false
    };
  },
  methods:{
    deleteTask(id){
      console.log(id, "burası");
      this.tasks = this.tasks.filter((task) => task._id !== id)
    },
    addTodo(todo){
      console.log(todo);
      this.tasks = [...this.tasks, todo]
    },
    toggleForm(){
      this.showTodo = !this.showTodo
    }
  }
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap");
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: "Poppins", sans-serif;
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

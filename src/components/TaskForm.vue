<template>
  <form @submit="onSubmit" class="add-form">
    <div class="form-control">
      <label>Task</label>
      <input type="text" v-model="text" name="text" placeholder="Add Task" />
    </div>
    <div class="form-control form-control-check"></div>

    <input type="submit" value="Save Task" class="btn btn-block" />
  </form>
</template>

<script>
export default {
  name: "TaskForm",
  data() {
    return {
      text: "",
    };
  },
  methods:{
    onSubmit(e){
        e.preventDefault();
        if(!this.text){
           return alert("Please type something")
        }
        const newTask = {
            _id: Math.floor(Math.random() * 1000),
            text:this.text
        }
        // console.log(newTask);
        this.$emit("addTodo", newTask)
        this.text = ""
    }
  }
};
</script>

<style scoped>
.add-form {
  margin-bottom: 40px;
}
.form-control {
  margin: 20px 0;
}
.form-control label {
  display: block;
}
.form-control input {
  width: 100%;
  height: 40px;
  margin: 5px;
  padding: 3px 7px;
  font-size: 17px;
}
</style>

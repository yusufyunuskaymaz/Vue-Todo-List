<template>
  <div class="task">
    <h3>
      {{ task.text }}

      <i v-on:click="onClickDone(task._id)" class="fas fa-times"></i>
    </h3>
  </div>
</template>

<script>
export default {
  name: "TaskA",
  props: {
    task: Object,
  },
  methods:{
    onClickDone(id){
        this.$emit("DeleteTask", id)
    }
  }
};
</script>

<style>
.fas {
  color: red;
}
.task {
  background: #f4f4f4;
  margin: 5px;
  padding: 10px 20px;
  cursor: pointer;
}
.task.reminder {
  border-left: 5px solid green;
}
.task h3 {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>

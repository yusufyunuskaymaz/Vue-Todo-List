<template>
    <div :key="task._id" v-for="task in tasks">
        <TaskA @DeleteTask="deleteTask($event)" :task="task" />
        
    </div>
</template>

<script>
import TaskA from './Task.vue';
export default {
    name:"TasksA",
    props:{
        tasks:Array
    },
    components:{
        TaskA
    },
    methods:{
        deleteTask(id){
            this.$emit("deleteTask", id)
            // alert(id)
        }
    }
}
</script>
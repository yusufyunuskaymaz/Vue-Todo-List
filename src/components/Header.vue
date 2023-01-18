<template>
    <header>
        <h1>{{title}}</h1>
        <ButtonA @toggleForm="toggleForm($event)" :text="showForm ? 'Close' : 'Add Task' "></ButtonA>
    </header>
</template>

<script>
import ButtonA from './ButtonA.vue';
export default {
    name: "HeaderDeneme",
    props: {
        title: String,
        showForm:Boolean
    },
    components: { ButtonA },
    methods:{
        toggleForm(){
            this.$emit("toggleForm")
        }
    }
}
</script>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}
</style>
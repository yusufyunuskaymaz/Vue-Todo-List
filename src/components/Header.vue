<template>
    <header>
        <h1>{{title}}</h1>
        <ButtonA text="Add Task2"></ButtonA>
    </header>
</template>

<script>
import ButtonA from './ButtonA.vue';
export default {
    name: "HeaderDeneme",
    props: {
        title: String
    },
    components: { ButtonA }
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
<template>
    <button @click="toggleForm" class="btn">{{text}}</button>
</template>

<script>
export default{
    name:"ButtonA",
    props:{
        text:String
    },
    methods:{
        toggleForm(){
            this.$emit("toggleForm")
        }
    }
}
</script>
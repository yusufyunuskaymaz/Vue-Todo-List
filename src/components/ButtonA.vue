<template>
    <button @click="toggleForm" :style="{background: color }" class="btn btn-{{ color }}">{{text}}</button>
</template>

<script>

export default{
    name:"ButtonA",
    props:{
        text:String,
        color:String,
    },
    methods:{
        toggleForm(){
            this.$emit("toggleForm")
        }
    }
}
</script>
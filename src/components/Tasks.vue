<template>
    <div :key="task.id" v-for="task in tasks">
       <Task2 @toggle-reminder="$emit('toggle-reminder',task.id)" @delete-task="$emit('delete-task',task.id)" :task="task"/>
    </div>
</template>

<script>
import Task2 from "./Task.vue"
    export default {
        name:"Tasks",
        props: {
            tasks:Array
        },
        components:{
            Task2
        },
        emits:['delete-task','toggle-reminder']
    }
</script>
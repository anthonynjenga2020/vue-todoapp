<template>
    <div>
        <h2>TODO LIST</h2>
        <TodoItem
            :v-for="todo in todos"
            :key="todo.id"
            :todo="todo"
            @toggle="handleToggle"
        />
    </div>
</template>

<script>
import TodoItem from './TodoItem.vue';

export default {
    components: {
        TodoItem,
    },
    props: ['todos'],
    methods:{
        handleToggle(id){
            this.$emit('toggle', id);
        },
    },

};


</script>
<template>
  <div>
    <TodoList :todos="todos" @toggle="handleToggle"></TodoList>
    <input v-model="newTodo" />
    <button @click="addTodo">Add</button>
    
  </div>
</template>

<script>
import TodoList from './components/TodoList.vue';

export default {
  components: {
    TodoList
  },
  data() {
    return{
      todos:[
        {id: 1, text: 'lambalolo', completed:false },
        {id: 2, text: 'kumanina', completed:true },
      ],
      newTodo: '',
    }
  },
  methods: {
      handleToggle(id) {
        //update the completion of the todo item
        const index = this.todos.findIndex(todo => todo.id === id);
        if (index !== -1) {
          this.todos[index].completed = !this.todos[index].completed;
        }
      },

      addTodo() {
        //add a new todo item
        if (this.newTodo.trim() !== '') {
          this.todos.push({
            id: this.todos.length + 1,
            text: this.newTodo,
            completed: false,
          }) 
          //to clear the input
          this.newTodo = '';
        }
      }
  }
}

</script>
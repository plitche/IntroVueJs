<template>
  <div id="app" class="container">
    <h1 class="text-center">Todo App</h1>
    <input 
      type="text" 
      class="w-100 p-2" 
      placeholder="Type todo"
      @keyup.enter="addTodo"
      v-model="todoText"
      />
    <hr/>
    <Todo 
      v-for="todo in todos" 
      :key="todo.id"
      :todo="todo" 
      @toggle-checkbox="toggleCheckbox"
      @click-delete="clickDelete"
      />
  </div>
</template>

<script>
import Todo from '@/components/Todo.vue';

export default {
  components: {
    Todo
  },
  data() {
    return {
      todoText: '',
      todos: [
        { id: 1, text: 'buy a car', checked:false},
        { id: 2, text: 'play game', checked:false},
      ]
    }
  },
  methods: {
    addTodo(e) {
      console.log(e);
      console.log(this.todos.length)
      this.todos.push({
        id: this.todos.length + 1,
        text: e.target.value,
        checked: false
      })
      this.todoText = '';
    },
    toggleCheckbox({id, checked}) {
      console.log(id, checked)
      const index = this.todos.findIndex(todo => {
        return todo.id === id;
      });
      this.todos[index].checked = checked;
    },
    clickDelete(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    }
  }
}
</script>

<template>
  <div id="app">
	<b-navbar toggleable="lg" type="dark" variant="info">
		<b-navbar-brand href="#">My Todo list</b-navbar-brand>
	</b-navbar>
	<b-container fluid class="mt-3">
	<b-row>
	<b-col>
    <Todos v-bind:todos="todos" v-on:delete-todo="deleteTodo"/>
	</b-col>
	</b-row>
	<b-row>
	<b-col>
    <AddTodo v-on:add-todo="addTodo"/>
	</b-col>
	</b-row>
  </b-container>
  </div>
</template>
<script>
import Todos from './components/Todos';
import AddTodo from './components/AddTodo';
export default {
  name: 'app',
  components: {
    Todos,
    AddTodo
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: 'Go workout',
          completed: false
        },
        {
          id: 2,
          title: 'Do laundry',
          completed: false
        },
        {
          id: 3,
          title: 'Cook food',
          completed: false
        },
        {
          id: 4,
          title: 'Clean up room',
          completed: false
        },
        {
          i: 5,
          title: 'Finish work',
          completed: false
        }
      ],
    }
  },
  methods: {
    addTodo(newTodoObj) {
      this.todos = [...this.todos, newTodoObj];
    },
    deleteTodo(todoId) {
      this.todos = this.todos.filter(todo => todo.id !== todoId);
    }
  }
}
</script>

<style>
</style>

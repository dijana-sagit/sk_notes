<template>
  <div>
	<b-list-group  v-bind:key="todo.id" v-for="todo in todos">
		<b-list-group-item>
			<Todo v-bind:todo="todo" v-on:delete-todo="$emit('delete-todo', todo.id)"/>
		</b-list-group-item>
	</b-list-group>
	</div>
</template>
<script>
import Todo from './Todo';
export default {
  name: 'Todos',
  components: {
    Todo
  },
  props: [
    "todos"
  ]
}
</script>
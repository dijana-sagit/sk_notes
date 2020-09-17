<template>
	<div class="d-flex w-100 justify-content-between">
      <h5 class="mb-1"  v-bind:class="{ 'completed': todo.completed }">{{ todo.title }}</h5>
	<b-button-group pill>
      <b-button  variant="outline-info" v-on:click="markComplete">{{todo.completed ? "Uncheck" : "Check"}}</b-button>
      <b-button  @click="$emit('delete-todo', todo.id)" variant="outline-danger">Delete</b-button>
    </b-button-group>
    </div>  
</template>
<script>
export default {
  name: 'Todo',
  props: [
    "todo"
  ],
  methods: {
    markComplete() {
      this.todo.completed = !this.todo.completed
    }
  }
}
</script>
<style scoped>
  .completed {
    text-decoration: line-through;
  }
</style>
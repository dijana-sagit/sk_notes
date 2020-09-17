<template>
  <b-form @submit="addTodo">
	<b-input-group class="mt-3">
	<b-form-input  v-model="title" name="title"></b-form-input>
	<b-input-group-append>
		<b-button variant="primary" type="submit">Add</b-button>
	</b-input-group-append>
	</b-input-group>
  </b-form>
</template>
<script>

export default {
  name: 'AddTodo',
  data() {
    return {
      title: ''
    }
  },
  methods: {
    addTodo(e) {
      e.preventDefault();
      const newTodoObj = {
        id: this.$uuid.v4(),
        title: this.title,
        completed: false
      }
      console.log(newTodoObj);
      this.$emit('add-todo', newTodoObj);
      this.title = '';
    }
  }
}
</script>
<style scoped>
</style>
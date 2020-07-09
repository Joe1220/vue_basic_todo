<template>
  <div>
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
import Todo from "@/components/Todo.vue"
export default {
  computed: {
    todos() {
      return this.$store.state.todo.todos
    }
  },
  components: {
    Todo
  },
  methods: {
    toggleCheckbox(value) {
      this.$emit("toggle-checkbox", value)
    },
    clickDelete(todoId) {
      this.$emit("click-delete", todoId)
    }
  }
}
</script>

<style scoped></style>

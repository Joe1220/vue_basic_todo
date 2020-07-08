<template>
  <div id="app" class="container">
    <h1 class="text-center">Todo App</h1>
    <CompletedTodo />
    <AddTodo />
    <div>
      <hr />
      <TodoList />
    </div>
  </div>
</template>

<script>
import TodoList from "@/components/TodoList.vue"
import AddTodo from "@/components/AddTodo.vue"
import CompletedTodo from "@/components/CompletedTodo.vue"
export default {
  components: { TodoList, AddTodo, CompletedTodo },
  methods: {
    addTodo(value) {
      this.todos.push({
        id: Math.random(),
        text: value,
        checked: false
      })
    },
    toggleCheckbox({ id, checked }) {
      const index = this.todos.findIndex((todo) => {
        return todo.id === id
      })
      this.todos[index].checked = checked
    },
    clickDelete(id) {
      this.todos = this.todos.filter((todo) => todo.id !== id)
    }
  },
  data() {
    return {
      // todos: [
      //   { id: 1, text: "buy a car", checked: false },
      //   { id: 2, text: "buy a car", checked: false }
      // ]
    }
  }
}
</script>

<style></style>

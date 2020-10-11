<template>
  <div class="todo-item" v-bind:class="{ 'is-complete': todo.complete }">
    <p>
      <input type="checkbox" v-on:change="markTodoComplete" />
      {{ todo.title }}
      <button @click="$emit('del-todo', todo.id)" class="delete">x</button>
    </p>
  </div>
</template>

<script>
export default {
  name: "Todo",
  props: ["todo"],
  methods: {
    markTodoComplete() {
      this.todo.complete = !this.todo.complete;
    },
  },
};
</script>

<style scoped>
.is-complete {
  text-decoration: line-through;
}

.todo-item {
  background: #e5e5e5;
  border-bottom-color: #a4a4a4;
  padding: 1px;
  text-align: left;
}

.delete {
  text-align: right;
}
</style>
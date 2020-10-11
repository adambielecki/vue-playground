<template>
  <div v-bind:class="{'is-complete' : todo.complete}">
      <h3>{{todo.title}}</h3>
    </div>
</template>

<script>
export default {
  name: "Todo",
  props: ["todo"]
};
</script>

<style scoped>

.is-complete{
  text-decoration: line-through;
}
</style>
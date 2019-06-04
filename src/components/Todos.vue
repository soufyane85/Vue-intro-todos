<template>
  <div>
    <div v-for="t in todos" v-bind:key="t.id">
      <TodoItem v-bind:todo="t" v-on:del-todo="$emit('del-todo', t.id)"/>
    </div>
  </div>
</template>

<script>
import TodoItem from "./TodoItem.vue";
export default {
  name: "Todos",
  components: {
    TodoItem
  },
  props: ["todos"]
};
</script>

<style scoped>
</style>

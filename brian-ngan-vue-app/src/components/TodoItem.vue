<template>
  <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
    <p>
      <input type="checkbox" name="" id="" v-on:change="markComplete">
      {{todo.title}}</p>
      <button @click="$emit('del-todo', todo.id)" class="del">x</button>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    markComplete() {
      this.todo.completed =!this.todo.completed;
    }
    }
}
</script>

<style scoped>
.todo-item{
  font-weight: 900;
}
.is-complete {
  text-decoration: line-through;
}
.del{
  color: red;
}

 ;


</style>
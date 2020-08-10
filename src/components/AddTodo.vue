<template>
  <div>
    <form @submit="addTodo">
      <input type="text" v-model="title" name="title">
      <input type="submit" value="submit" class="btn">
    </form>
  </div>
</template>

<script>
// import {v4 as uuid} from 'uuid';

export default {
  name: "AddTodo",
  data() {
      return {
        title: ''
      }
  },
  methods: {
    addTodo(e) {
      e.preventDefault();
        const newTodo = {
        // id: uuid(),
        title: this.title,
        completed: false
      }
    // Send up to parent
    this.$emit('add-todo', newTodo);
    this.title ='';
    }
  }
}
</script>

<style lang="stylus" scoped>

</style>
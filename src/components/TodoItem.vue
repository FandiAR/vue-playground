<template>
  <div class="playground-container">
    <div class="todo-item" v-bind:class="{'is-complete':propsTodo.completed}">
      <p>
        <input type="checkbox" v-on:change="isCompleted" v-model="propsTodo.completed" checked="propsTodo.completed === true" />
        {{ propsTodo.title }}
        <button @click="$emit('del-todo', propsTodo.id)" class="del">x</button>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["propsTodo"],
  methods: {
    isCompleted() {
      this.propsTodo.completed = true;
    }
  }
};
</script>

<style scoped>
.todo-item {
  background: whitesmoke;
  padding: 10px;
  border-bottom: dotted 1px grey;
  color: black;
}
.todo-item p {
  text-align: left;
}
.is-complete {
  text-decoration: line-through;
  color: #72a065;
}
.del {
  background: #eb373e;
  color: white;
  border: none;
  padding: 5px 9px;
  border-radius: 50%;
  cursor: pointer;
  float: right;
}
</style>
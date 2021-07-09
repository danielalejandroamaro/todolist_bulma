<template>
  <div class="box">
    <div class="columns">
      <div class="column is-flex-grow-0">
        <label class="checkbox">
          <input type="checkbox" v-model="todo.isDone">
        </label>
      </div>
      <div class="column is-flex-shrink-0 has-text-left" :class="{'tachado':todo.isDone}">
        {{todo.text}}
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: "todocard",
    props: ["todo"]
  }
</script>

<style scoped>

  .tachado {
    text-decoration: line-through;
  }
</style>

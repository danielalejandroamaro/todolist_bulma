<template>
  <div class="hello">
    <card-creator :createNew="createNew"></card-creator>

    <section class="section">
      <h1 class="title">Todos</h1>
      <h2 class="subtitle">
        todos pendientes
      </h2>
      <todocard
          v-for="todo of pendingTodos"
          :todo="todo"
      ></todocard>

    </section>
    <section class="section">
      <h2 class="subtitle">
        todos done
      </h2>
      <todocard
          v-for="todo of doneTodos"
          :todo="todo"
      ></todocard>

    </section>


  </div>
</template>

<script>
  import todocard from "./todocard";
  import cardCreator from "./cardCreator";

  export default {
    name: 'HelloWorld',
    components: {todocard, cardCreator},

    data() {
      return {
        todolist: []
      };
    },

    methods: {
      async createNew(params) {
        console.log("llegue fuera del componente");
        // throw new Error("esto esploto");
        this.todolist.push({
          ...params, isDone: false
        })
      }
    },

    computed: {
      pendingTodos() {
        return this.todolist.filter(todo => !todo.isDone);
      },
      doneTodos() {
        return this.todolist.filter(todo => todo.isDone);
      }
    },

    props: {
      msg: String
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="less">
  h3 {
    margin: 40px 0 0;
  }

  ul {
    list-style-type: none;
    padding: 0;
  }

  li {
    display: inline-block;
    margin: 0 10px;
  }

  a {
    color: #42b983;
  }
</style>

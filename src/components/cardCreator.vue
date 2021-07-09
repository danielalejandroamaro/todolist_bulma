<template>
  <div class="columns">
    <div class="control column">
      <input v-model="text" class="input" type="text" placeholder="Normal input">
      <div v-if="message_error">
        <p class="help has-text-danger">{{message_error}}</p>
      </div>
    </div>
    <div class="column is-flex-grow-0">
      <button class="button is-success" @click="loadValue">
        <span class="icon is-small">
          <i class="fas fa-check"></i>
        </span>
      </button>
    </div>
  </div>
</template>

<script>
  export default {
    name: "cardCreator",

    props: ["createNew"],

    data() {
      return {
        text: "",
        message_error: ""
      };
    },
    methods: {
      loadValue() {
        let text = this.text;
        let self = this;
        this.createNew({text}).then(
          () => {
            self.text = "";
            self.mesage_error = "";
          }
        ).catch(() => {
          self.mesage_error = "a ocurrido un error";
        })
      }
    }
  }
</script>

<style scoped>

</style>

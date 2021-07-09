<template>

  <section class="section">
    <div class="container">
      <img alt="Vue logo" src="../assets/logo.png">
      <div class="home">
        <HelloWorld msg="Welcome to Your Vue.js App"/>
      </div>
    </div>
  </section>

</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld
  }
}
</script>

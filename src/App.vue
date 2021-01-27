<template>
  <template v-if="user">
    <Message :username="user"/>
  </template>
  <template v-else>
    <h1>Type username</h1>
  </template>

  <p><input type="text" v-model="user"></p>
  <button @click="increment(10)">Increment</button>
  {{ count }}

  <Task />
</template>

<script>
import Message from './components/Message.vue'
import Task from './components/Task.vue'

export default {
  name: 'App',
  data() {
    return {
      user: '',
      count: 0
    }
  },
  components: {
    Message,
    Task
  },
  methods: {
    increment(num) {
      this.count += num
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

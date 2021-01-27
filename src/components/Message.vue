<template>
  <h1>welcome {{ username }}!</h1>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    username: String
  }
}
</script>

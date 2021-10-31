<template>
  <div class="about">
    <h1>This is a form</h1>
    <p>Fill this in you!</p>
  </div>

    <Form />
</template>


<script>
import Form from '../components/Form.vue'

export default {
    name: 'App',
    components: { Form }
}
</script>


<style scoped>

body {
  margin: 0;
  background: #eee;
}

</style>
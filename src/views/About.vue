<template>
  <div class="about">
    <h1>Contact</h1>
    <p>For all enquiries, please email us using the form below:</p>
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
  cursor: default;
}

</style>
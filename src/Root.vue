<template>
  <div id="app">
    <!-- <login /> -->
    <init-form />
  </div>
</template>

<script>
import Login from './components/Login.vue'
import InitForm from './components/Form.vue'

export default {
  name: 'root',

  components: { Login, InitForm }
}
</script>

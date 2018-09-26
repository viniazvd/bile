<template>
  <c-input-container v-bind="$attrs" class="c-input">
    <input
      class="input"
      v-bind="$attrs"
      :value="value"
      @input="v => $emit('input', v.target.value)"
    >
  </c-input-container>
</template>

<script>
import CInputContainer from './CInputContainer'
export default {
  components: { CInputContainer },
  props: {
    value: String
  }
}
</script>

<style>
.c-input { display: flex; flex-direction: column; }
.input {
  outline: 0;
  height: 34px;
  border-radius: 5px;
  transition: box-shadow .3s ease;
}
</style>

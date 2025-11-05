<template>
  <div>Hello, {{ message }}</div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'

export default defineComponent({
  name: 'E01Instance',
  setup() {
    const name = 'Dong hun Kim'
    const message = ref(name)
    
    return {
      message
    }
  }
})
</script>

<style scoped>
div {
  color: blue;
  font-size: 20px;
  font-weight: bold;
}
</style>

<template>
  <div>
    <input ref="inputField" type="text" placeholder="Click the button to focus" />
    <button @click="focusInput">Focus Input</button>
  </div>
</template>

<script setup>
import { ref, onMounted, onBeforeMount, onBeforeUpdate, onUpdated, onBeforeUnmount, onUnmounted } from 'vue'

const inputField = ref(null)

const focusInput = () => {
  if (inputField.value) {
    inputField.value.focus()
  }
}

onMounted(() => {
  console.log(inputField)
  if(inputField.value) {
    inputField.value.focus()
  }
})

onBeforeMount(() => console.log(inputField))
onMounted(() => console.log(inputField))
onBeforeUpdate(() => console.log(inputField))
onUpdated(() => console.log(inputField))
onBeforeUnmount(() => console.log(inputField))
onUnmounted(() => console.log(inputField))
</script>

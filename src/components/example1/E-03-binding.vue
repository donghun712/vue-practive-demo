<template>
  <div>
    <input v-model="id" />
    <input v-model="password" />
    <p>{{ message }}</p>
    <button @click="whoami">whoami</button>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'

export default defineComponent({
  name: 'E03Binding',
  setup() {
    const message = ref('Hello Vue')
    const id = ref('')
    const password = ref('')

    const whoami = () => {
      message.value = id.value + ' ' + password.value
    }

    return {
      message,
      id,
      password,
      whoami
    }
  }
})
</script>

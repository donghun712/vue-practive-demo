<template>
  <div>
    <p>{{ message }}</p>
    <p>{{ id }}</p>
    <p>{{ password }}</p>
    <button @click="sendEvent">Send Event</button>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'ChildComponent',
  props: {
    message: {
      type: String,
      required: true
    },
    id: {
      type: [String, Number],
      required: true
    },
    password: {
      type: [String, Number],
      required: true
    }
  },
  setup(props, { emit }) {
    const sendEvent = () => {
      emit('custom-event', 'Hello from child')
    }
    return {
      ...props,
      sendEvent
    }
  }
})
</script>

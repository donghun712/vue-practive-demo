<template>
  <div>
    <h2>{{ title }}</h2>
    <p>Full Name: {{ fullName }}</p>
    <input v-model="firstName" placeholder="First Name" />
    <input v-model="lastName" placeholder="Last Name" />
    <button @click="greet">Greet</button>
    <p>Greeting Count: {{ greetCount }}</p>
    <p>{{ message }}</p>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref, computed, watch, onBeforeMount, onMounted, onBeforeUpdate, onUpdated, onBeforeUnmount, onUnmounted } from 'vue'

export default defineComponent({
  name: 'E07OptionsAPI',
  props: {
    title: {
      type: String,
      default: 'User Information'
    }
  },
  setup(props) {
    const firstName = ref('John')
    const lastName = ref('Doe')
    const greetCount = ref(0)
    const message = ref('')
    const fullName = computed(() => `${firstName.value} ${lastName.value}`)
    const greet = () => {
      greetCount.value++
      message.value = `Hello, ${fullName.value}!`
    }
    const resetGreetCount = () => {
      greetCount.value = 0
    }
    watch(greetCount, (newValue, oldValue) => {
      console.log(`Greet count changed from ${oldValue} to ${newValue}`)
      if (newValue >= 3) {
        message.value = "That's enough greetings for now!"
      }
    })
    onBeforeMount(() => console.log('beforeMount hook'))
    onMounted(() => console.log('mounted hook'))
    onBeforeUpdate(() => console.log('beforeUpdate hook'))
    onUpdated(() => console.log('updated hook'))
    onBeforeUnmount(() => console.log('beforeUnmount hook'))
    onUnmounted(() => console.log('unmounted hook'))

    // props.title은 반환하지 않아도 템플릿에서 바로 사용 가능!
    return {
      firstName,
      lastName,
      message,
      greetCount,
      greet,
      resetGreetCount,
      fullName
    }
  }
})
</script>

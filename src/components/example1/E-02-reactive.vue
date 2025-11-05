<template>
  <div>{{ fullName }}</div>
</template>

<script lang="ts">
import { defineComponent, ref, computed, onMounted } from 'vue'

export default defineComponent({
  name: 'E02Reactive',
  setup() {
    const firstName = ref('Donghun')
    const lastName = ref('Kim')

    const fullName = computed(() => firstName.value + ' ' + lastName.value)

    onMounted(() => {
      console.log('mounted')

      let a = 10

      setTimeout(() => {
        a = 20
        console.log(a)
      }, 500)

      setTimeout(() => {
        lastName.value = '123'
      }, 1000)

      setTimeout(() => {
        firstName.value = 'KDH'
      }, 2000)
    })

    return {
      firstName,
      lastName,
      fullName
    }
  }
})
</script>

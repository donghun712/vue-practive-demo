<template>
  <div>
    <ChildComponent
      :message="parentMessage"
      :id="1"
      :password="1234"
      @custom-event="handleEvent"
    />
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'
import ChildComponent from './ChildComponent.vue'

export default defineComponent({
  name: 'E05ParentComponent',
  components: {
    ChildComponent
  },
  setup() {
    const parentMessage = ref('Hello from parent')
    
    // methods는 setup에서 함수로 정의
    const handleEvent = (payload: any) => {
      console.log(payload)
    }

    return {
      parentMessage,
      handleEvent
    }
  }
})
</script>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  props: {
    text: {
      type: String,
      default: 'Button',
    },
  },
  emits: ['click'],
  setup() {
    return {}
  },
})
</script>
<template>
  <button class="button" @click="() => $emit('click')">{{ text }}</button>
</template>
<style scoped>
.button {
  padding: 0.75rem 0.5rem;
}
</style>

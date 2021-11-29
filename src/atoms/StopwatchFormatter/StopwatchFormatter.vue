<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  props: {
    count: {
      type: Number,
      default: 0,
    },
  },
})
</script>
<template>
  <div class="timer">
    <span>{{ ('0' + Math.floor(count / 6000)).slice(-2) }}</span
    >: <span>{{ ('0' + Math.floor((count / 100) % 60)).slice(-2) }}</span>
    <span class="fs">{{ ('0' + Math.floor(count % 100)).slice(-2) }}</span>
  </div>
</template>
<style scoped>
.timer {
  display: flex;
  justify-content: center;
  align-items: flex-end;
  font-size: 36px;
}
.fs {
  margin-left: 10px;
}
</style>

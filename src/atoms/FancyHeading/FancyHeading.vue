<script>
import { defineComponent } from 'vue'

export default defineComponent({
  components: {},
  props: {
    title: {
      type: String,
      default: 'Title',
    },
  },
  setup() {
    return {}
  },
})
</script>
<template>
  <h1>{{ title }}</h1>
</template>
<style lang="scss" scoped></style>

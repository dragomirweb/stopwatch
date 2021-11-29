<script lang="ts">
import { defineComponent } from 'vue'
import { Container, FancyHeading } from './atoms/index'
import { StopWatch } from './molecules/index'

export default defineComponent({
  components: { Container, FancyHeading, StopWatch },
  props: {},
  setup() {
    return {}
  },
})
</script>
<template>
  <Container>
    <nav>
      <FancyHeading title="Stopwatch" />
    </nav>
    <StopWatch />
  </Container>
</template>
<style scoped>
nav {
  display: flex;
  justify-content: center;
  font-size: 48px;
  line-height: 48px;
}
</style>

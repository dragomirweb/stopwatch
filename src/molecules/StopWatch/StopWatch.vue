<script>
import { defineComponent, ref } from 'vue'

import { useSubscription } from '@vueuse/rxjs'
import { interval, Subject } from 'rxjs'
import { takeUntil } from 'rxjs/operators'

import { StopwatchFormatter, CustomButton } from '../../atoms'

export default defineComponent({
  components: {
    StopwatchFormatter,
    CustomButton,
  },
  setup() {
    const count = ref(0)
    const unsubscribe = new Subject(false)

    const start = () => {
      count.value = 0
      useSubscription(
        interval(10)
          .pipe(takeUntil(unsubscribe))
          .subscribe(() => {
            count.value = count.value + 1
          })
      )
    }

    const stop = () => {
      unsubscribe.next(true)
    }

    return {
      count,
      start,
      stop,
    }
  },
})
</script>
<template>
  <StopwatchFormatter :count="count" />
  <div class="actions">
    <CustomButton text="Start" @click="start" />
    <CustomButton class="ml-2" text="Stop" @click="stop">Stop</CustomButton>
  </div>
</template>
<style scoped>
.actions {
  display: flex;
  justify-content: center;
  margin-top: 2rem;
}

.ml-2 {
  margin-left: 1.25rem;
}
</style>

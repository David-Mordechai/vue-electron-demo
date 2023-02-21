<template>
  <div>
    <button @click="incrementCount">Clicked {{ count }} times</button>
  </div>
</template>

<script>
import useCounter from './composables/useCounter';
export default {
  name: "click-counter-composition",
  setup() {
    const { count, incrementCount } = useCounter(5, 10)

    return {
      count,
      incrementCount
    }
  }
};
</script>

<style scoped></style>

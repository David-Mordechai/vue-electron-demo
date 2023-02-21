<template>
  <div>
    <h2 @mouseover="incrementCount">Hovered {{ count }} times</h2>
  </div>
</template>

<script>
import useCounter from './composables/useCounter';
export default {
  name: "hover-counter-composition",
  setup() {
    const { count, incrementCount } = useCounter()

    return {
      count,
      incrementCount
    }
  }
};
</script>

<style scoped></style>

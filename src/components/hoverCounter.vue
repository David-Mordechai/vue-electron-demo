<template>
  <div>
    <h2 @mouseover="incrementCount">Hovered {{ count }} times</h2>
  </div>
</template>

<script>
import CounterMixin from "../mixins/counter";
export default {
  name: "hover-counter",
  mixins: [CounterMixin],
};
</script>

<style scoped></style>

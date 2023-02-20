<template>
  <div>
    <button @click="incrementCount">Clicked {{ count }} times</button>
  </div>
</template>

<script>
import CounterMixin from "../mixins/counter";
export default {
  name: "click-counter",
  mixins: [CounterMixin],
};
</script>

<style scoped></style>

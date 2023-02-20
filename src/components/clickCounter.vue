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
  data() {
    return {
        count: 100 // this count is overriding the mixin count
    }
  },
};
</script>

<style scoped></style>

<template>
  <div>
    <h2>{{ name }}</h2>
    <button @click="setName">Change Name</button>
    <h2>{{ count }}</h2>
    <button @click="incrementCount">Increment Count</button>
    <h2>{{ first }} {{ last }}</h2>
    <button @click="changeHero">Change Hero</button>
  </div>
</template>

<script>
import { ref, reactive, toRefs } from "vue";
export default {
  name: "methods-composition",
  data() {
    return {
      name: "David",
    };
  },
  methods: {
    setName() {
      this.name = "Simon";
    },
  },
  setup() {
    const count = ref(0);
    const state = reactive({
        first: 'Brace',
        last: 'Wayne'
    })

    function incrementCount() {
      count.value++;
    }

    function changeHero() {
        state.first = 'Clark'
        state.last = 'kent'
    }

    return {
      count,
      incrementCount,
      ...toRefs(state),
      changeHero
    };
  },
};
</script>

<style scoped></style>

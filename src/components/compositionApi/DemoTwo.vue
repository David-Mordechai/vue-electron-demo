<template>
  <h2>{{ firstName }} {{ lastName }}</h2>
</template>

<script>
import { reactive, toRefs } from "vue";
export default {
  name: "demo-two",
  setup() {
    const state = reactive({
        firstName: 'Bruce',
        lastName: 'Wayne'
    })

    return toRefs(state)
  },
};
</script>

<style scoped></style>

<template>
  <div>
    <h2>{{ name }}</h2>
  </div>
</template>

<script>
import { ref } from "vue";
export default {
  name: "demo-one",
  setup() {
    let name = ref("David");

    setTimeout(() => {
      name.value = "David2";
    }, 2000);
    return {
      name,
    };
  },
};
</script>

<style scoped></style>

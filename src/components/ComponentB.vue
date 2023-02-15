<template>
  <div>
    <component-c />
  </div>
</template>

<script>
import ComponentC from "./ComponentC.vue";
export default {
  name: "component-b",
  components: { ComponentC },
  data() {
    return {};
  },
};
</script>

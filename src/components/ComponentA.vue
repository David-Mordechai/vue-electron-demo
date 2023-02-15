<template>
  <div>
    <h2>Component A user name - {{ name }}</h2>
    <component-b />
  </div>
</template>

<script>
import ComponentB from "./ComponentB.vue";
export default {
  name: "component-a",
  components: { ComponentB },
  data() {
    return {
      name: "David",
    };
  },
  provide() {
    return {
      userName: this.name,
    };
  },
};
</script>

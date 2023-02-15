<template>
  <div>
    <h2>Component C user name - {{ userName }}</h2>
  </div>
</template>

<script>
export default {
  name: "component-c",
  data() {
    return {};
  },
  inject: ['userName'],
};
</script>

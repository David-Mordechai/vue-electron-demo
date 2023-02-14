<script>
import  FilesBrowser from "./components/FilesBrowser.vue";
import Learning from "./components/Learning.vue";
import Watchers from "./components/Watchers.vue";

export default {
  components: { FilesBrowser, Learning, Watchers }
};
</script>

<template>
  
  <FilesBrowser />
  <Learning />
  <Watchers />
</template>

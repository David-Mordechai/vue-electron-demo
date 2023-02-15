<template>
  <FilesBrowser />
  <hr />
  <Learning />
  <hr />
  <Watchers />
  <hr />
  <Article title="Article Title" :likes="50" :isPublished="true" id="my-article" />
  <hr />
  <ComponentA />
  <hr />
  <button @click="showPopup = true">Show popup</button>
  <Popup v-show="showPopup" @close="closePopup" />
  <hr>
  <Input v-model="name" />
</template>

<script>
import Article from "./components/Article.vue";
import FilesBrowser from "./components/FilesBrowser.vue";
import Learning from "./components/Learning.vue";
import Watchers from "./components/Watchers.vue";
import ComponentA from "./components/ComponentA.vue";
import Popup from "./components/Popup.vue";
import Input from "./components/input.vue";
export default {
  components: { FilesBrowser, Learning, Watchers, Article, ComponentA, Popup, Input },
  data() {
    return {
      showPopup: false,
      name: ''
    };
  },
  methods: {
    closePopup(name) {
      this.showPopup = false;
      console.log(name);
    },
  },
};
</script>

<style>
#app {
  text-align: center !important;
}
</style>

<script>
import Article from "./components/Article.vue";
import FilesBrowser from "./components/FilesBrowser.vue";
import Learning from "./components/Learning.vue";
import Watchers from "./components/Watchers.vue";
import ComponentA from "./components/ComponentA.vue";
import Popup from "./components/Popup.vue";
export default {
  components: { FilesBrowser, Learning, Watchers, Article, ComponentA, Popup },
  data() {
    return {
      showPopup: false,
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

<template>
  <FilesBrowser />
  <hr />
  <Learning />
  <hr />
  <Watchers />
  <hr />
  <Article
    title="Article Title"
    :likes="50"
    :isPublished="true"
    id="my-article"
  />
  <hr />
  <ComponentA />
  <hr />
  <button @click="showPopup = true">Show popup</button>
  <Popup v-show="showPopup" @close="closePopup" />
</template>

<style>
body {
  text-align: center !important;
}
</style>

<template>
  <div>
    <h2>Article component</h2>
    <h2 v-bind="$attrs">{{ title }}</h2>
    <h2>Likes - {{ likes }}</h2>
    <h2>Is published - {{ isPublished ? "Yes" : "No" }}</h2>
  </div>
</template>

<script>
export default {
  name: "article-vue",
  props: {
    title: {
      type: String,
      required: true,
      default: "Article default value",
    },
    likes: Number,
    isPublished: Boolean,
  },
  inheritAttrs: false,
};
</script>

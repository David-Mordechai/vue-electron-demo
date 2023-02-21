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
  <hr />
  <Input v-model="name" />
  <hr />
  <NameList>
    <template v-slot:default="slotProps">
      {{ slotProps.firstName }} {{ slotProps.lastName }}
    </template>
  </NameList>
  <NameList>
    <template v-slot:default="slotProps">
      {{ slotProps.lastName }} {{ slotProps.firstName }}
    </template>
  </NameList>
  <NameList>
    <template v-slot:default="slotProps">
      {{ slotProps.firstName }}
    </template>
  </NameList>
  <hr />
  <div>
    <button @click="activeTab = 'tab-a'">Tab A</button>
    <button @click="activeTab = 'tab-b'">Tab B</button>
    <button @click="activeTab = 'tab-c'">Tab C</button>
    <keep-alive>
      <component :is="activeTab"></component>
    </keep-alive>
  </div>
  <hr />
  <ClickCounter />
  <HoverCounter />
  <hr />
  <Data />
  <hr />
  <DemoOne />
  <DemoTwo />
  <hr>
  <Methods />
</template>

<script>
import Article from "./components/Article.vue";
import FilesBrowser from "./components/FilesBrowser.vue";
import Learning from "./components/Learning.vue";
import Watchers from "./components/Watchers.vue";
import ComponentA from "./components/ComponentA.vue";
import Popup from "./components/Popup.vue";
import Input from "./components/input.vue";
import NameList from "./components/NameList.vue";
import TabA from "./components/TabA.vue";
import TabB from "./components/TabB.vue";
import TabC from "./components/TabC.vue";
import { myFunc, myFunc2 } from "./services/restService.js";
import ClickCounter from "./components/clickCounter.vue";
import HoverCounter from "./components/hoverCounter.vue";
import Data from "./components/compositionApi/Data.vue";
import DemoOne from "./components/compositionApi/DemoOne.vue";
import DemoTwo from "./components/compositionApi/DemoTwo.vue";
import Methods from "./components/compositionApi/Methods.vue";

export default {
  components: {
    FilesBrowser,
    Learning,
    Watchers,
    Article,
    ComponentA,
    Popup,
    Input,
    NameList,
    TabA,
    TabB,
    TabC,
    ClickCounter,
    HoverCounter,
    Data,
    DemoOne,
    DemoTwo,
    Methods,
  },
  created() {
    console.log(myFunc());
    console.log(myFunc2());
  },
  data() {
    return {
      showPopup: false,
      name: "",
      activeTab: "tab-a",
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

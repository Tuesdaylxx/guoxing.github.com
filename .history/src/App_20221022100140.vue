<template>
  <div id="app">
    <!-- 头部 -->
    <top-header />
    <!-- <router-view /> -->
    <!-- 主体 -->
    <home />
    <!-- 固定导航 -->
    <tool-bar />
    <!-- 底部 -->
    <serve-footer />
  </div>
</template>
<script>
import TopHeader from "./components/TopHeader.vue";
import Home from "./views/Home.vue";
import ToolBar from "./components/ToolBar.vue";
import ServeFooter from "./components/ServeFooter.vue";

export default {
  data() {
    return {};
  },
  components: {
    TopHeader,
    Home,
    ToolBar,
    ServeFooter,
  },
};
</script>

<style>
@import "./assets/css/base.css";
#app {
  width: 100%;
}
.bulk {
  width: 1100px;
  margin: 0 auto;
}
</style>

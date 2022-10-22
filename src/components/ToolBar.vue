<template>
  <div class="tool-bar">
    <div class="title">服务项目</div>
    <div class="item" v-for="(item, index) in barData" :key="index">
      {{ item }}
    </div>
  </div>
</template>

<script>
export default {
  name: "ToolBar",
  components: {},
  data() {
    return {
      barData: [
        "新车",
        "二手车",
        "分期",
        "新车",
        "二手车",
        "分期",
        "新车",
        "二手车",
        "分期",
      ],
    };
  },
};
</script>

<style scoped>
.tool-bar {
  position: fixed;
  right: 1%;
  top: 200px;
  width: 60px;
  font-size: 15px;
  z-index: 999;
}
.title {
  height: 56px;
  background: #c70009;
  padding: 5px 15px;
  color: #fff;
  opacity: 1;
}
.item {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 37px;
  background: #000;
  color: #fff;
  opacity: 0.7;
  border-bottom: 1px solid #fff;
  cursor: pointer;
}
.item:hover {
  background: #c70009;
}
</style>

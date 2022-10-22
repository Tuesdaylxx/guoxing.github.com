<template>
  <div class="serve-footer">
    <div class="bulk">
      <h4>服务项目</h4>
      <div class="box">
        <div class="item" v-for="item of 10" :key="item"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ServeFooter",
  components: {},
};
</script>

<style scoped>
.serve-footer {
  height: 335px;
  margin-top: 100px;
  border-top: 2px solid #c70009;
  background: #f2f2f2;
}
.box {
  display: flex;
  justify-content: space-between;
}
h4 {
  padding: 10px 0;
  color: #666;
}
.item {
  width: 92px;
  height: 76px;
  background-color: #eaebed;
  cursor: pointer;
}
.item:hover {
  background-color: #d9d9d9;
}
</style>

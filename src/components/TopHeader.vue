<template>
  <div class="top-header">
    <!-- 左logo -->
    <div class="top-container bulk">
      <div class="logo">
        <img src="../assets/images/logo.png" alt="" />
      </div>
      <!-- 右电话 -->
      <div class="phone">
        <div class="phone-text">
          <img src="../assets/images/header_phone.png" alt="" />
          服务热线
        </div>
        <div class="phone-number">
          <p>010-6617 0971 / 6611 0788</p>
          <p>010-6611 8657 / 6611 3156</p>
        </div>
      </div>
    </div>
    <!-- 导航 -->
    <div class="nav-container">
      <ul class="nav bulk">
        <li
          class="nav-item"
          @mouseenter="itemHover(item)"
          @mouseleave="itemRecovery(item)"
          v-for="(item, index) in navsData"
          :key="index"
        >
          <div class="item-style">
            <a :href="item.url">{{ item.value }}</a>
          </div>
          <span class="nav-span" v-show="index !== navsData.length - 1">|</span>
          <div v-show="item.hover && item.info" class="info">
            <div class="triangle"></div>
            <p>{{ item.info }}</p>
          </div>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "TopHeader",
  components: {},
  data() {
    return {
      navsData: [
        {
          value: "首页",
          url: "javascript:void(0);",
          hover: false,
          info: "车型丰富，价格优惠",
        },
        {
          value: "新车购买",
          url: "javascript:void(0);",
          hover: false,
          info: "车型丰富，价格优惠",
        },
        {
          value: "二手车服务",
          url: "javascript:void(0);",
          hover: false,
        },
        {
          value: "关于我们",
          url: "javascript:void(0);",
          hover: false,
          info: "车型丰富，价格优惠",
        },
        {
          value: "新车购买",
          url: "javascript:void(0);",
          hover: false,
        },
        {
          value: "二手车服务",
          url: "javascript:void(0);",
          hover: false,
        },
        {
          value: "关于我们",
          url: "javascript:void(0);",
          hover: false,
          info: "车型丰富，价格优惠",
        },
        {
          value: "新车购买",
          url: "javascript:void(0);",
          hover: false,
          info: "车型丰富，价格优惠",
        },
        {
          value: "二手车服务",
          url: "javascript:void(0);",
          hover: false,
          info: "车型丰富，价格优惠",
        },
        {
          value: "关于我们",
          url: "javascript:void(0);",
          hover: false,
          info: "车型丰富，价格优惠",
        },
      ],
    };
  },
  methods: {
    itemHover(item) {
      item.hover = true;
    },
    itemRecovery(item) {
      item.hover = false;
    },
  },
};
</script>

<style scoped>
.top-container {
  display: flex;
  justify-content: space-between;
  height: 90px;
}
.top-container .logo {
  align-self: center;
}
.top-container .logo img {
  width: 316px;
}
/* 电话 */
.phone {
  display: flex;
  height: 100%;
  align-items: center;
}
.phone-text {
  margin-right: 10px;
}
.phone-text img {
  width: 20px;
  vertical-align: middle;
}
.phone-number p {
  font-size: 20px;
  color: #ac0000;
  line-height: 26px;
}
/* 导航 */
.nav-container {
  width: 100%;
  height: 45px;
  background: #c70009;
}
.nav-container ul {
  display: flex;
}

.item-style {
  display: inline-block;
}
.item-style a {
  display: inline-block;
  padding: 0 15px;
  font-size: 18px;
  color: #fff;
  line-height: 45px;
}

.nav-item:hover {
  background-color: rgb(168, 0, 10);
}
.nav-span {
  width: 1px;
  height: 15px;
  color: rgb(130, 0, 6);
}
.nav-item {
  position: relative;
}
.info .triangle {
  position: absolute;
  bottom: -7px;
  left: 50%;
  transform: translateX(-50%);
  background-color: #ac0000;
  width: 15px;
  height: 15px;
  transform: rotate(45deg);
  z-index: 9;
}
.info p {
  position: absolute;
  top: 45px;
  left: 0;
  white-space: nowrap;
  background-color: #fff;
  padding: 25px 35px;
}
</style>

<template>
  <div class="home">
    <div class="banner">
      <img src="../assets/images/banner.png" alt="" />
    </div>
    <!-- 下条幅区 -->
    <div class="sub-channel">
      <div class="bulk">
        <div class="sub-item" v-for="(item, index) in subData" :key="index">
          <img class="sub-icon" :src="item.url" alt="123" />
          <a :href="item.url"></a>
          <div class="sub-text">
            <h3>{{ item.title }}</h3>
            <p>{{ item.text }}</p>
          </div>
        </div>
      </div>
    </div>
    <!-- 主体区 -->
    <div class="main-content">
      <div class="goods bulk">
        <div class="title">
          <h1>新车购买</h1>
          <a class="more" href="#">全部></a>
        </div>
        <div class="goods-content">
          <div class="goods-left">
            <!-- 第一行 -->
            <div class="car-type">
              <div class="item">
                <img src="../assets/images/goods_icon01.png" alt="" />
                小轿车
              </div>
              <div class="item">
                <img src="../assets/images/goods_icon01.png" alt="" />
                SUV
              </div>
              <div class="item">
                <img src="../assets/images/goods_icon01.png" alt="" />
                MPV
              </div>
              <div class="item">
                <img src="../assets/images/goods_icon01.png" alt="" />
                新能源汽车
              </div>
              <div class="item all">全部></div>
            </div>
            <!-- 第二行 -->
            <div class="car-price">
              <div class="item">10万以下</div>
              <div class="item">10-15万</div>
              <div class="item">15-20万</div>
              <div class="item">20-30万</div>
              <div class="item">30万以上</div>
            </div>
            <!-- 第三行 -->
            <div class="car-name1">
              <div class="item">
                <img src="../assets/images/goods_icon02.png" alt="" />
                小轿车
              </div>
              <div class="item white">威然</div>
              <div class="item white">威然</div>
              <div class="item white"></div>
              <div class="item white"></div>
            </div>
            <div class="car-name2">
              <div class="item">
                <img src="../assets/images/goods_icon02.png" alt="" />
                小轿车
              </div>
              <div class="item white">XC60</div>
              <div class="item white">S60</div>
              <div class="item white">XC60</div>
              <div class="item white">S60</div>
            </div>
            <div class="car-name2">
              <div class="item">
                <img src="../assets/images/goods_icon02.png" alt="" />
                小轿车
              </div>
              <div class="item white">威然</div>
              <div class="item white">威然</div>
              <div class="item white"></div>
              <div class="item white"></div>
            </div>
          </div>
          <div class="goods-right">
            <div class="discount">全部优惠></div>
            <img
              :src="item.url"
              class="swiper"
              v-show="index == imgIndex"
              v-for="(item, index) in swiper"
              :key="index"
              @click="next(index)"
            />
            <div class="dot">
              <div
                class="dot-item"
                :class="{ active: index == imgIndex }"
                @click="jump(index)"
                v-for="(item, index) in swiper.length"
                :key="index"
              ></div>
            </div>
          </div>
        </div>
      </div>
      <div class="commend bulk">
        <!--  <div class="title">
          <h1>价值优选</h1>
          <a class="more" href="#">更多></a>
        </div> -->
      </div>
      <div class="trading"></div>
      <div class="question"></div>
      <div class="news"></div>
      <div class="partners"></div>
    </div>

    <!-- <img alt="Vue logo" src="../assets/logo.png" /> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App" /> -->
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "Home",
  components: {
    HelloWorld,
  },
  data() {
    return {
      imgIndex: 0,
      timer: "", // 轮播定时器
      subData: [
        {
          title: "价格优",
          text: "厂家直供 集采价格",
          url: require("../assets/images/banner_icon01.png"),
        },
        {
          title: "品牌多",
          text: "车型丰富 一站选购",
          url: require("../assets/images/banner_icon02.png"),
        },
        {
          title: "价格优",
          text: "厂家直供 集采价格",
          url: require("../assets/images/banner_icon01.png"),
        },
        {
          title: "品牌多",
          text: "车型丰富 一站选购",
          url: require("../assets/images/banner_icon02.png"),
        },
      ],
      swiper: [
        { url: require("../assets/images/goods_car01.png") },
        { url: require("../assets/images/goods_car011.png") },
      ],
    };
  },
  methods: {
    next(index) {
      if (this.imgIndex < this.swiper.length - 1) {
        this.imgIndex = index + 1;
      } else {
        this.imgIndex = 0;
      }
    },
    jump(index) {
      this.imgIndex = index;
    },
    play() {
      clearInterval(this.timer);
      this.timer = setInterval((index) => {
        if (this.imgIndex < this.swiper.length - 1) {
          this.imgIndex++;
        } else {
          this.imgIndex = 0;
        }
      }, 5000);
    },
  },
  mounted() {
    this.play();
  },
};
</script>

<style scoped>
.banner {
  width: 100%;
  height: 430px;
  cursor: pointer;
}

/* 下条幅区 */
.sub-channel {
  height: 108px;
  background: #f4f5f7;
}
.sub-channel .bulk {
  display: flex;
  height: 100%;
  justify-content: space-between;
}
.sub-item {
  display: flex;
  align-items: center;
}
.sub-item img {
  width: 68px;
  height: 68px;
  margin-right: 10px;
}
.sub-text p {
  font-size: 14px;
  color: #333;
  line-height: 19px;
  margin-top: 7px;
}
/* 公共标题 */
.title {
  position: relative;
  height: 110px;
  text-align: center;
}
.title h1 {
  height: 48px;
  font-size: 48px;
  color: #c70009;
  line-height: 110px;
}
.title .more {
  position: absolute;
  top: 73px;
  right: 0;
  font-size: 14px;
  color: #333;
  line-height: 14px;
  cursor: pointer;
}
.title .more:hover {
  color: #c70009;
}
/* 公共部分结束 */

/* 新车购买 */
.goods-content {
  display: flex;
  height: 415px;
}
/* 新车左边 */
.goods-left {
  width: 737px;
  border-top: 2px solid #c70009;
  color: #333;
}

.goods-left > div {
  display: flex;
  height: 82px;
}
.goods-left .item {
  display: flex;
  flex: 25%;
  border: 1px solid #fff;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background: #f4f5f7;
  cursor: pointer;
}
.goods-left .item:hover {
  background-color: #ddd;
  color: #c70009;
}
.goods-left .all {
  font-weight: normal;
}
.goods-left .white {
  background-color: #fff;
  border-bottom: 1px dotted #bdbdbd;
}
.goods-left .white:hover {
  background-color: #fff;
}
.car-type img {
  width: 56px;
  height: 23px;
}
.car-type,
.car-price {
  font-size: 14px;
  font-weight: bold;
}
.car-name1 img,
.car-name2 img,
.car-name3 img {
  width: 48px;
  height: 27px;
}

/* 新车右边 */
.goods-right {
  position: relative;
  float: right;
  width: 363px;
  cursor: pointer;
}
.goods-right .discount {
  position: absolute;
  top: 0;
  right: 0;
  width: 75px;
  height: 30px;
  background: #fff;
  text-align: center;
  line-height: 30px;
  font-size: 14px;
  color: #333;
  cursor: pointer;
  opacity: 0.6;
}
.goods-right .discount:hover {
  color: #c70009;
}
.goods-right img {
  width: 100%;
  height: 100%;
}
.goods-right .dot {
  display: flex;
  position: absolute;
  bottom: 10px;
  right: 30px;
  cursor: pointer;
}
.goods-right .dot-item {
  width: 10px;
  height: 10px;
  margin: 5px;
  background: #fff;
}
.goods-right .active {
  background-color: #c70009;
}
</style>

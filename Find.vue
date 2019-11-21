<template>
  <scroll-view top="46px" bottom="50px">
    <div id="page">
      <van-swipe :autoplay="3000" indicator-color="white">
        <van-swipe-item v-for="(image, index) in images" :key="index">
          <img class="swiper_img" :src="image" />
        </van-swipe-item>
      </van-swipe>
    </div>
  </scroll-view>
</template>
<script>
import ScrollView from "./ScrollView.vue";
export default {
  components: {
    "scroll-view": ScrollView
  },
  data() {
    return {
      images: [
        "https://img.yzcdn.cn/vant/apple-1.jpg",
        "https://img.yzcdn.cn/vant/apple-2.jpg"
      ]
    };
  },
  methods: {},
  mounted() {}
};
</script>
<style scoped>
#page {
  width: 100%;
  height: auto;
}
.swiper_img {
  width: 100vw;
  height: calc(var(--hsl) * 375vw);
}
</style>

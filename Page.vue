<template>
  <section>
    <van-nav-bar :title="title" :left-arrow="false" :fixed="true" />
    <transition>
      <keep-alive>
        <home v-if="active==0"></home>
        <classify v-else-if="active==1"></classify>
        <shop-car v-else-if="active==2"></shop-car>
        <find v-else-if="active==3"></find>
        <mine v-else-if="active==4"></mine>
      </keep-alive>
    </transition>
    <van-tabbar v-model="active">
      <van-tabbar-item icon="home-o">首页</van-tabbar-item>
      <van-tabbar-item icon="apps-o">分类</van-tabbar-item>
      <van-tabbar-item icon="shopping-cart-o">购物车</van-tabbar-item>
      <van-tabbar-item icon="point-gift-o">发现</van-tabbar-item>
      <van-tabbar-item icon="user-o">我的</van-tabbar-item>
    </van-tabbar>
  </section>
</template>
<script>
import Home from "./Home.vue";
import Classify from "./Classify.vue";
import shopCar from "./shopCar.vue";
import Find from "./Find.vue";
import Mine from "./Mine.vue";
export default {
  components: {
    home: Home,
    classify: Classify,
    "shop-car": shopCar,
    find: Find,
    mine: Mine
  },
  data() {
    return {
      active: 0
    };
  },
  computed: {
    title: function() {
      let title = "首页";
      switch (this.active) {
        case 0:
          title = "首页";
          break;
        case 1:
          title = "分类";
          break;
        case 2:
          title = "购物车";
          break;
        case 3:
          title = "发现";
          break;
        case 4:
          title = "我的";
          break;
      }
      return title;
    }
  },
  methods: {},
  mounted() {}
};
</script>
<style>
.van-nav-bar--fixed {
  background: linear-gradient(to right, #ff9700, #ed1c24);
}
.van-nav-bar__title {
  color: #fff;
}
.van-tabbar-item--active {
  color: #f65a10;
}
</style>

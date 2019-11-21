<template>
  <scroll-view top="46px" bottom="50px" @getScrollTop="getScrollTop" @reachBottom="onReachBottom">
    <div id="page">
      <van-pull-refresh v-model="isLoading" @refresh="onRefresh">
        <div v-for="(item,index) in 100" :key="index">this is home</div>
      </van-pull-refresh>
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
      isLoading: false
    };
  },
  methods: {
    onRefresh() {
      setTimeout(() => {
        this.$toast("刷新成功");
        this.isLoading = false;
        this.count++;
      }, 500);
    },
    getScrollTop(e){
      window.console.log(e)
    },
    //触底事件
    onReachBottom(){
      window.console.log('触底');
    }
  },
  mounted() {
    this.$toast("重载");
  }
};
</script>
<style scoped>
#page {
  width: 100%;
  min-height: 100%;
}
</style>

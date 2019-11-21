<template>
  <div
    id="contanier"
    @scroll="getScroll"
    :style="`top:${top};bottom:${bottom};background-color:${backColor}`"
  >
    <slot></slot>
  </div>
</template>
<script>
export default {
  props: {
    top: {
      type: String,
      default: "0px"
    },
    bottom: {
      type: String,
      default: "0px"
    },
    backColor: {
      type: String,
      default: "#fff"
    }
  },
  data() {
    return {
      scrollTop: 0
    };
  },
  methods: {
    //滚动事件
    getScroll(e) {
      let wScrollY = e.target.scrollTop; // 当前滚动条位置
      this.scrollTop = wScrollY;
      let wInnerH = e.target.clientHeight; // 设备窗口的高度（不会变）
      let bScrollH = e.target.scrollHeight; // 元素总高度
      if (wScrollY + wInnerH >= bScrollH) {
        this.$emit("reachBottom");
      }
    }
  },
  activated() {
    this.$el.scrollTop = this.scrollTop;
    this.$emit('getScrollTop',{scrollTop:this.scrollTop});
  },
  updated() {},
  mounted() {}
};
</script>
<style scoped>
#contanier {
  width: 100%;
  position: fixed;
  z-index: 1;
  left: 0px;
  overflow-y: scroll;
  display: flex;
  display: -webkit-flex;
  flex-wrap: wrap;
}
</style>

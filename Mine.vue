<template>
  <scroll-view top="46px" bottom="50px">
    <div id="page">this is mine</div>
  </scroll-view>
</template>
<script>
import ScrollView from "./ScrollView.vue";
export default {
  components: {
    "scroll-view": ScrollView
  },
  data() {
    return {};
  },
  methods: {},
  mounted() {}
};
</script>
<style scoped>
#page {
  width: 100%;
  min-height: 100%;
}
</style>

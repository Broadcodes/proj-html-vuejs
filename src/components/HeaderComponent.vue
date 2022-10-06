<template>
  <div class="header">
    <HeaderAreaTop />
    <HeaderAreaBottom />
  </div>
</template>

<script>
import HeaderAreaTop from './HeaderAreaTop.vue';
import HeaderAreaBottom from './HeaderAreaBottom.vue';
export default {
  name: "HeaderComponent",
  components: { HeaderAreaTop, HeaderAreaBottom }
}
</script>

<style lang="scss" scoped>
.header {
  position: fixed;
  z-index: 200;
  width: 100%;
  background-color: #fff;
}
</style>
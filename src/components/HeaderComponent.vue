<template>
  <div>
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

</style>
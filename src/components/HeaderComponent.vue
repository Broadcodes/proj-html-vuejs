<template>
  <div class="header" @click="getValueSearch('')">
    <HeaderAreaTop @searchInput="getValueSearch" :numProducts="producsInCart" @pageHome="getPage" @showCart="getValueShowCart"/>
    <HeaderAreaBottom :menu="dataShop" @pageSelected="getPage" @elementMenuSelected="getElementMenuSelected" @showCart="getValueShowCart"
      @elementAnimalCategory="getElementAnimalCategory" :pageActive="setPageActive"/>
  </div>
</template>

<script>
import HeaderAreaTop from './HeaderAreaTop.vue';
import HeaderAreaBottom from './HeaderAreaBottom.vue';
export default {
  name: "HeaderComponent",
  data() {
    return {
      valuePageFromHeader: this.valuePage,
    }
  },
  components: {
    HeaderAreaTop,
    HeaderAreaBottom
  },
  props: {
    dataShop: Array,
    producsInCart: Number,
    setPageActive: String
  },
  methods: {
    getPage(value) {
      this.$emit('page', value);
    },
    getValueSearch(value) {
      this.$emit('search', value);
    },
    getElementMenuSelected(value) {
      this.$emit('elementMenu', value);
    },
    getElementAnimalCategory(value){
      this.$emit('animalCategory', value);
    },
    getValueShowCart(value){
      this.$emit('showCart', value);
    }
  }
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
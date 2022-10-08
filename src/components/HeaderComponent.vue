<template>
  <div class="header" @click="getValueSearch('')">
    <HeaderAreaTop @searchInput="getValueSearch" :numProducts="producsInCart" @pageHome="getPage"/>
    <HeaderAreaBottom :menu="dataShop" @pageSelected="getPage" @elementMenuSelected="getElementMenuSelected" :pageActive="setPageActive"/>
  </div>
</template>

<script>
import HeaderAreaTop from './HeaderAreaTop.vue';
import HeaderAreaBottom from './HeaderAreaBottom.vue';
export default {
  name: "HeaderComponent",
  data(){
    return{
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
  methods:{
    getPage(value){
      this.$emit('page', value);
    },
    getValueSearch(value){
      this.$emit('search', value);
    },
    getElementMenuSelected(value){
      this.$emit('elementMenu', value);
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
<template>
  <div class="header">
    <HeaderAreaTop @searchInput="getValueSearch"/>
    <HeaderAreaBottom :menu="dataShop" @pageSelected="getPage"/>
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
  },
  methods:{
    getPage(value){
      this.$emit('page', value);
    },
    getValueSearch(value){
      this.$emit('search', value);
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
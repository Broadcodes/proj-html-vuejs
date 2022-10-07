<template>
  <div id="app">
    <header>
      <HeaderComponent :dataShop="shop" @page="getPage" @search="getValueSearch" :producsInCart="productNumbers" :setPageActive="pageSelected"/>
    </header>
    <main>
      <SearchBar v-if="this.textSearch !== ''" />
      <div v-else>
        <MainComponent v-if="this.pageSelected === 'Home'" :dataShop="shop" :dataFeedback="feedback" :dataBlog="blog"
          @productsNumber="numberProductsInCart" @page="getPage" />
        <ShopComponent v-else-if="this.pageSelected === 'Shop'" :dataShop="shop" @cart="numberProductsInCart" />
        <AboutComponent v-else-if="this.pageSelected === 'About'" />
        <BlogComponent v-else-if="this.pageSelected === 'Blog'" />
        <ContactComponent v-else-if="this.pageSelected === 'Contact'" />
        <BrandComponent v-else-if="this.pageSelected === 'Brand'" />
      </div>

    </main>
    <footer>
      <FooterComponent />
    </footer>
  </div>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue';
import MainComponent from './components/MainComponent.vue';
import FooterComponent from './components/FooterComponent.vue';
import ShopComponent from './components/ShopComponent.vue';
import AboutComponent from './components/AboutComponent.vue';
import BlogComponent from './components/BlogComponent.vue';
import ContactComponent from './components/ContactComponent.vue';
import BrandComponent from './components/BrandComponent.vue';

import { shop } from '@/data';
import { feedback } from '@/data';
import { blog } from '@/data';
import SearchBar from './components/SearchBar.vue';






export default {
  name: 'App',
  data() {
    return {
      pageSelected: '',
      textSearch: '',
      shop,
      feedback,
      blog,
      productNumbers: 0
    }
  },
  components: {
    HeaderComponent,
    MainComponent,
    FooterComponent,
    ShopComponent,
    AboutComponent,
    BlogComponent,
    ContactComponent,
    BrandComponent,
    SearchBar
  },
  methods: {
    getPage(value) {
      this.pageSelected = value;
    },
    getValueSearch(value) {
      this.textSearch = value;
    },
    numberProductsInCart(value) {
      this.productNumbers += value;
    }
  },
  created() {
    this.pageSelected = 'Home';
  }
}
</script>

<style lang="scss">
* {
  box-sizing: border-box;
  margin: 0px;
  padding: 0px;
}

body {
  font-family: sans-serif;
}

#app {
  cursor: url('@/assets/img/cursor.png'), auto;
  scroll-behavior: smooth;

  main {
    padding-top: 112px;
  }
}
</style>

<template>
  <div id="app">
    <header>
      <HeaderComponent :dataShop="shop" @page="getPage" @elementMenu="elementSelected" @search="getValueSearch"
        :producsInCart="productNumbers" :setPageActive="pageSelected" @animalCategory="getAnimalCategory" />
    </header>
    <main>
      <SearchBar v-if="this.textSearch !== ''" :dataShop="shop" :searchElementUser="textSearch"
        @cart="numberProductsInCart" />
      <div v-else>
        <MainComponent v-if="this.pageSelected === 'Home'" :dataShop="shop" :dataFeedback="feedback" :dataBlog="blog"
          @productsNumber="numberProductsInCart" @page="getPage" />
        <ShopComponent v-else-if="this.pageSelected === 'Shop'" :dataShop="shop" @cart="numberProductsInCart"
          :setAnimalCategory="animalCategory" />
        <AboutComponent v-else-if="this.pageSelected === 'About'" @page="getPage" />
        <BlogComponent v-else-if="this.pageSelected === 'Blog'" />
        <ContactComponent v-else-if="this.pageSelected === 'Contact'" />
        <BrandComponent v-else-if="this.pageSelected === 'Brand'" :dataShop="shop" :brandSelected="elementMenuSelected"
          @cart="numberProductsInCart" />
      </div>

    </main>
    <footer>
      <FooterComponent :dataShop="shop" @page="getPage" />
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
import SearchBar from './components/SearchBar.vue';

import { shop } from '@/data';
import { feedback } from '@/data';
import { blog } from '@/data';

export default {
  name: 'App',
  data() {
    return {
      pageSelected: '',
      elementMenuSelected: '',
      textSearch: '',
      shop,
      feedback,
      blog,
      productNumbers: 0,
      animalCategory: ''
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
    elementSelected(value) {
      this.elementMenuSelected = value
    },
    getValueSearch(value) {
      this.textSearch = value;
    },
    numberProductsInCart(value) {
      this.productNumbers += value;
    },
    getAnimalCategory(value) {
      this.animalCategory = value;
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

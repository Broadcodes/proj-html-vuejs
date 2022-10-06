<template>
  <div id="app">
    <header>
      <HeaderComponent :dataShop="shop" />
    </header>
    <main>
      <MainComponent :dataShop="shop" :dataFeedback="feedback" />
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

import { shop } from '@/data';
import { feedback } from '@/data';

export default {
  name: 'App',
  data() {
    return {
      shop,
      feedback,
    }
  },
  components: {
    HeaderComponent,
    MainComponent,
    FooterComponent
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

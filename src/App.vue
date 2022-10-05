<template>
  <div id="app">
    <header>
      <HeaderComponent />
    </header>
    <main>
      <MainComponent />
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


export default {
  name: 'App',
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
}
</style>

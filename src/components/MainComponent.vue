<template>
  <div>
    <!-- Sezione relativa alla barra verde sopra alla jumbotron -->
    <div class="bannerTopJumbo">

    </div>
    <!-- Sezione relativa alla jumbotron dell'homepage -->
    <JumboTronArea />
    <!-- Sezione relativa alla barra verde inferiore alla jumbotron -->
    <div class="bannerBottomJumbo">

    </div>
    <!-- Sezione relativa alla Categoria dei prodotti -->
    <BrowseByCategory />
    <!-- Sezione relativa alla vendita alimentare dell'animale -->
    <FoodShopArea />
    <!-- Sezione relativa ai nuovi arrivi settimanali -->
    <NewArrivalsWeekly />
    <!-- Sezione relativa ai prodotti in vendita -->
    <ProductsForSale />
    <!-- Sezione relativa alle testimonianze -->
    <FeedbackUsers />
    <!-- Sezione relativa alle newsletter -->
    <NewsLetterArea />
    <!-- Sezione relativa agli articoli -->
    <ArticlesBlogArea />
    <!-- Sezione relativa agli accessori per cani e cibo per gatti -->
    <AreaDogsAndCats />
    <!-- Sezione relativa alla barra verde in cui sono presenti le icone sulla spedizione, store e i pagamenti -->
    <div class="bannerPay">

    </div>
    <!-- Sezione relativa ai nuovi arrivi per cani e gatti-->
    <NewProductsArrival />
  </div>
</template>

<script>
import JumboTronArea from './JumboTronArea.vue';
import BrowseByCategory from './BrowseByCategory.vue';
import FoodShopArea from './FoodShopArea.vue';
import NewArrivalsWeekly from './NewArrivalsWeekly.vue';
import ProductsForSale from './ProductsForSale.vue';
import FeedbackUsers from './FeedbackUsers.vue';
import NewsLetterArea from './NewsLetterArea.vue';
import ArticlesBlogArea from './ArticlesBlogArea.vue';
import AreaDogsAndCats from './AreaDogsAndCats.vue';
import NewProductsArrival from './NewProductsArrival.vue';
export default {
  name: "MainComponent",
  components: {
    JumboTronArea,
    BrowseByCategory,
    FoodShopArea,
    NewArrivalsWeekly,
    ProductsForSale,
    FeedbackUsers,
    NewsLetterArea,
    ArticlesBlogArea,
    AreaDogsAndCats,
    NewProductsArrival
}
}
</script>

<style lang="scss" scoped>

</style>
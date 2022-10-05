<template>
  <div>
    <!-- Sezione relativa alla barra verde sopra alla jumbotron -->
    <div class="bannerTopJumbo">
      <ul>
        <li><i class="fa-regular fa-map"></i><span>International</span>Shipping Services</li>
        <li><i class="fa-regular fa-clock"></i>See our<span>store hours</span>and services</li>
        <li><i class="fa-solid fa-check"></i>We price match to give you the<span>best deals</span></li>
      </ul>
    </div>
    <!-- Sezione relativa alla jumbotron dell'homepage -->
    <JumboTronArea />
    <!-- Sezione relativa alla barra verde inferiore alla jumbotron -->
    <div class="bannerBottomJumbo">
      <img src="../assets/images/food-transparent-5-400x223.png" alt="croccantini">
      <p>Get $25 OFF your first purchase of our homemade pet food!</p>
      <a href="#">Visit the shop</a>
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
.bannerTopJumbo,
.bannerBottomJumbo{
  background-color: #1e3120;
  background-image: url('@/assets/images/bg-transparent-3.png');
  background-size: 15%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.bannerTopJumbo{
  height: 50px;

  ul{
    list-style-type: none;
    display: flex;
    justify-content: space-between;
    width: 80%;

    li{
      width: calc(100% / 3);
      color: rgb(208, 208, 208);
      font-size: 0.75rem;
      text-align: center;

      i,
      span{
        padding: 0 5px;
        color: #fff;
      }

      span{
        font-weight: 600;
      }
    }
  }
}

.bannerBottomJumbo{
  height: 110px;
  
  img{
    height: 70%;
  }
  
  p{
    color: #fff;
    margin: 0 25px;
    font-size: 0.9rem;
  }

  a{
    color: rgb(189, 189, 189);
    font-size: 0.9rem;
  }
}
</style>
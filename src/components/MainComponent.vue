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
    <JumboTronArea @page="typePage" />
    <!-- Sezione relativa alla barra verde inferiore alla jumbotron -->
    <div class="bannerBottomJumbo">
      <img src="../assets/images/food-transparent-5-400x223.png" alt="croccantini">
      <div class="text">
        <p>Get $25 OFF your first purchase of our homemade pet food!</p>
        <p @click="typePage('Shop')">Visit the shop</p>
      </div>
    </div>
    <!-- Sezione relativa alla Categoria dei prodotti -->
    <BrowseByCategory :data="dataShop"/>
    <!-- Sezione relativa alla vendita alimentare dell'animale -->
    <FoodShopArea @page="typePage" />
    <!-- Sezione relativa ai nuovi arrivi settimanali -->
    <NewArrivalsWeekly @page="typePage" />
    <!-- Sezione relativa ai prodotti in vendita -->
    <ProductsForSale :data="dataShop" @productInCart="quantityProducts" @page="typePage" />
    <!-- Sezione relativa alle testimonianze -->
    <FeedbackUsers :feedback="dataFeedback"/>
    <!-- Sezione relativa alle newsletter -->
    <NewsLetterArea />
    <!-- Sezione relativa agli articoli -->
    <ArticlesBlogArea :blog="dataBlog" @page="typePage"/>
    <!-- Sezione relativa agli accessori per cani e cibo per gatti -->
    <AreaDogsAndCats @page="typePage" />
    <!-- Sezione relativa alla barra verde in cui sono presenti le icone sulla spedizione, store e i pagamenti -->
    <div class="bannerPay">
      <div class="cards">
        <div class="card">
          <i class="fa-solid fa-truck"></i>
          <h4>Free worldwide deliveries</h4>
        </div>
        <div class="card">
          <i class="fa-regular fa-map"></i>
          <h4>Find stores near you</h4>
        </div>
        <div class="card">
          <i class="fa-solid fa-dollar-sign"></i>
          <h4>Best prices guarranteed</h4>
        </div>
        <div class="card">
          <i class="fa-regular fa-credit-card"></i>
          <h4>All credit card accepted</h4>
        </div>
      </div>
    </div>
    <!-- Sezione relativa ai nuovi arrivi per cani e gatti-->
    <NewProductsArrival :data="dataShop" />
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
  props:{
    dataShop: Array,
    dataFeedback: Array,
    dataBlog: Array
  },
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
  },
  methods:{
    quantityProducts(value){
      this.$emit('productsNumber', value);
    },
    typePage(value){
      this.$emit('page', value);
    }
  }
}
</script>

<style lang="scss" scoped>
.bannerTopJumbo,
.bannerBottomJumbo,
.bannerPay {
  background-color: #1e3120;
  background-image: url('@/assets/images/bg-transparent-3.png');
  background-size: 15%;
}

.bannerTopJumbo {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 50px;

  ul {
    list-style-type: none;
    display: flex;
    justify-content: space-between;
    width: 80%;

    li {
      width: calc(100% / 3);
      color: rgb(208, 208, 208);
      font-size: 0.75rem;
      text-align: center;

      i,
      span {
        padding: 0 5px;
        color: #fff;
      }

      span {
        font-weight: 600;
      }
    }
  }
}

.bannerBottomJumbo {
  height: 110px;
  position: relative;
  display: flex;

  img {
    height: 85%;
    position: absolute;
    bottom: 0px;
    left: 30%;
  }

  .text {
    position: absolute;
    bottom: 0px;
    left: 41%;
    height: 100%;
    display: flex;
    align-items: center;

    p {
      color: #fff;
      margin: 0 25px;
      font-size: 0.9rem;
    }

    p:nth-child(2) {
      color: rgb(189, 189, 189);
      font-size: 0.9rem;
      cursor: pointer;
      
      &:hover{
        text-decoration: underline;
      }
    }
  }
}

.bannerPay {
  .cards {
    display: flex;
    justify-content: space-evenly;
    padding: 15px;
    width: 100%;

    .card {
      width: calc(100vh / 4 - 20px);
      height: calc(100vh / 4 - 20px);
      margin: 0 10px;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      color: #fff;

      i {
        font-size: 2.5rem;
      }

      h4{
        font-size: 0.7rem;
        padding: 20px 0;
        color: rgb(203, 203, 203);
      }
    }
  }
}
</style>
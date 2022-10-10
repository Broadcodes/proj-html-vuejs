<template>
  <div class="container" id="kindsOfFood">
    <div class="cards">
      <div class="card">
        <h2>Kibble</h2>
        <h4>Dry dog food</h4>
        <img src="../assets/images/food-transparent-18-400x420.png" alt="Kibble Food">
        <input type="button" value="Shop dry food" @click="setproductInCart('Kibble')">
      </div>
      <div class="card">
        <h2>Moist</h2>
        <h4>Canned dog food</h4>
        <img src="../assets/images/food-transparent-17-400x420.png" alt="Moist Food">
        <input type="button" value="Shop moist food" @click="setproductInCart('Moist')">
      </div>
      <div class="card">
        <h2>Frozen</h2>
        <h4>Freeze-Dried dog food</h4>
        <img src="../assets/images/food-transparent-16-400x420.png" alt="Frozen Food">
        <input type="button" value="Shop frozen food" @click="setproductInCart('Frozen')">
      </div>
    </div>
  </div>
</template>

<script>
  import {shop} from '@/data';
  import {saveProducts} from '@/data';

export default {
  name: 'FoodShopArea',
  data(){
    return{
      shop,
      saveProducts
    }
  },
  methods: {
    setproductInCart(element) {

      this.shop.forEach(item => {
        if(item.name === element){
          this.saveProducts.push(item);
        }
      });
      
      let productQuantity = 0;
      this.$emit('productInCart', ++productQuantity);
    }
  }
}
</script>

<style lang="scss" scoped>
.container {
  width: 100%;
  padding: 50px 10%;

  .cards {
    width: 100%;
    display: flex;

    .card {
      background-color: #1e3120;
      background-image: url('@/assets/images/bg-transparent-3.png');
      width: calc(100% / 3 - 10px);
      margin: 0 5px;
      color: #fff;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      padding: 60px 0px;
      transition: transform .5s;

      &:hover {
        transform: scale(1.05);
        box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.3);
      }

      h2 {
        font-size: 1.8rem;
      }

      h4 {
        font-size: 0.85rem;
        color: #3d6f42;
        padding: 20px 0;
      }

      img {
        width: 60%;
        padding: 10px 0;
      }

      input {
        color: #fff;
        background-color: #3d6f42;
        border-radius: 25px;
        padding: 10px 20px;
        border: none;
        cursor: pointer;

        &:hover {
          background-color: #529258;
          color: #fff;
        }
      }
    }
  }
}
</style>
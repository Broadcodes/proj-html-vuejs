<template>
  <div class="container">
    <div class="areaTopImages">
      <div class="text">
        <h4>All-time best sellers</h4>
        <h2>Items everyone loves</h2>
      </div>
      <input type="button" value="View all products">
    </div>
    <div class="cards">
      <div class="card" v-for="item in getData()" :key="item.id">
        <img :src="item.img" :alt="item.name">
        <div class="addToCart">
          <i class="fa-regular fa-square"></i>
          <h3>ADD TO CART?</h3>
        </div>
        <div class="addedToCart">
          <i class="fa-regular fa-square-check"></i>
          <h3>VIEW CART</h3>
        </div>
        <h3>{{item.name}}</h3>
        <h4>{{item.price}}</h4>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ProductsForSale',
  props:{
    data: Array
  },
  methods: {
    getData() {
      let arr = [];

      this.data.forEach(element => {
        if (element.id === 14) {
          arr.push(element)
        }
        if (element.id === 13) {
          arr.push(element)
        }
        if (element.id === 12) {
          arr.push(element)
        }
        if (element.id === 11) {
          arr.push(element)
        }
      });

      return arr;
    }
  }
}
</script>

<style lang="scss" scoped>
.container {
  margin: 30px 10%;

  .areaTopImages {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 35px;

    .text {
      h4 {
        font-size: 0.8rem;
      }

      h2 {
        margin: 20px 0;
      }
    }

    input {
      padding: 10px 20px;
      border-radius: 25px;
      border: none;
      color: #fff;
      background-color: #3d6f42;
      cursor: pointer;

      &:hover {
        background-color: #529258;
        color: #fff;
      }
    }
  }

  .cards {
    display: flex;
    justify-content: space-between;

    .card {
      width: calc(100% / 4 - 20px);
      text-align: center;
      position: relative;

      .addToCart,
      .addedToCart {
        display: none;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        position: absolute;
        top: 0;
        width: 100%;
        height: 100%;

        h3 {
          color: #fff;
          transform: translateY(-25px);
        }

        i {
          color: #fff;
          padding: 20px;
          font-size: 1.8rem;
          background-color: rgba(0, 0, 0, 0.75);
          border-radius: 50px;
          transform: translateY(-25px);
        }
      }

      &:hover .addToCart {
        display: flex;
      }

      // .addedToCart{
      //   display: flex;
      // }

      &:hover img {
        filter: sepia(10%) brightness(85%);
      }

      img {
        width: 100%;
      }

      h3 {
        font-size: 0.9rem;
        padding: 10px;
      }

      h4 {
        font-size: 0.85rem;
        color: rgb(153, 153, 153);

        span {
          font-size: 0.7rem;
          padding: 10px;
          text-decoration: line-through #000;
        }
      }
    }
  }
}
</style>
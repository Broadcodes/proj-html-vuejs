<template>
  <div class="container">
    <ul class="cards">
      <li v-for="searchElement in this.getElement()" :key="searchElement.id">
        <div class="card">
          <img :src="searchElement.img" :alt="searchElement.name">
          <h2>{{searchElement.name}}</h2>
          <h3><span>Animal: </span> <span>{{searchElement.animal}}</span></h3>
          <h3><span>Quantity: </span> <span>{{searchElement.quantity}}</span></h3>
          <h3><span>Price: </span> <span>{{searchElement.price}}</span></h3>
          <input type="button" value="Add To Cart" @click="setQuantityCart()">
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'SearchBar',
  data() {
    return {
      quantity: 0
    }
  },
  props: {
    dataShop: Array,
    searchElementUser: String
  },
  methods: {
    getElement() {
      let arr = [];

      this.dataShop.forEach(element => {
        if (element.name.toLowerCase().includes(this.searchElementUser.toLowerCase())) {
          arr.push(element);
        }
      });

      return arr;
    },
    setQuantityCart() {
      this.quantity = 0;
      this.$emit('cart', ++this.quantity);
    }
  }

}
</script>

<style lang="scss" scoped>
.container {
  margin: 50px 10%;

  &>h2 {
    font-size: 2.5rem;
    margin: 30px 0 60px;
  }

  .cards {
    display: flex;
    list-style-type: none;
    width: 100%;
    flex-wrap: wrap;

    .card {
      display: flex;
      flex-direction: column;
      justify-content: space-around;
      column-gap: 20px;
      margin: 10px;
      max-width: 350px;
      padding: 50px;
      min-height: 570px;
      max-height: 570px;
      background-color: rgb(240, 234, 194);
      border-radius: 30px;

      img {
        width: 100%;
        max-width: 300px;
        border-radius: 50%;
        background-color: #f9f5f2;
      }

      h2 {
        padding: 20px 0;
      }

      h3 {
        padding: 5px 0px;

        span:nth-child(1) {
          color: rgb(126, 45, 45);
        }

        span:nth-child(2) {
          font-size: 1rem;
          padding: 0 10px;
        }
      }

      input {
        padding: 10px 20px;
        background-color: #fff;
        border-radius: 25px;
        border: none;
        margin: 10px;
        cursor: pointer;

        &:hover {
          background-color: #1e3120;
          color: #fff;
        }
      }
    }
  }
}
</style>
<template>
  <div class="container" id="newProductsArrival">
    <div class="text">
      <h2>New products arrival</h2>
      <p>Latest products</p>
    </div>
    <div class="contenitorCards">
      <!-- getdata restituisce gli elementi presenti nell'array data.js in base al valore dell'id passato da productID -->
      <div class="card" v-for="item in this.getData(this.productID)" :key="item.id">
        <img :src="item.img" :alt="item.name">
        <span v-if="item.id === 5" id="sale">Sale!</span>
        <h3>{{item.name}}</h3>
        <h4><span v-if="item.id === 5">$29.00</span>{{item.price}}</h4>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'NewProductsArrival',
  data() {
    return {
      productID: [8, 4, 5, 6, 7, 10]
    }
  },
  props: {
    data: Array
  },
  methods: {
    getData(id) {
      let arr = [];

      for (let i = 0; i < id.length; i++) {
        this.data.forEach(element => {
          if (element.id === id[i]) {
            arr.push(element)
          }
        })
      }

      return arr;
    }
  }
}
</script>

<style lang="scss" scoped>
.container {
  padding: 80px 10% 50px;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;

  .text {
    width: 50%;
    margin-bottom: 15px;

    h2 {
      font-size: 1.7rem;
    }

    p {
      line-height: 1.5rem;
      padding: 15px 0;
    }
  }

  .contenitorCards {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    width: 100%;
    margin-bottom: 40px;

    .card {
      position: relative;
      margin: 18px 5px;
      width: calc(100% / 3 - 10px);

      img {
        width: 100%;
      }

      #sale {
        position: absolute;
        top: 15px;
        left: 20px;
        background-color: #529258;
        color: #fff;
        padding: 8px 8px;
        border-radius: 50%;
        font-size: 0.9rem;

      }

      h3 {
        font-size: 0.9rem;
        padding: 8px 0;
      }

      h4 {
        color: rgb(136, 136, 136);
        font-size: 0.75rem;

        span {
          font-size: 0.6rem;
          padding: 10px;
          text-decoration: line-through #000;
        }
      }
    }
  }
}
</style>
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
      <div class="card">
        <img src="../assets/images/product-21-400x400.jpg" alt="Transport cage">
        <div class="addToCart">
          <i class="fa-regular fa-square"></i>
          <h3>ADD TO CART?</h3>
        </div>
        <div class="addedToCart">
          <i class="fa-regular fa-square-check"></i>
          <h3>VIEW CART</h3>
        </div>
        <h3>Transport cage</h3>
        <h4>$25.00</h4>
      </div>
      <div class="card">
        <img src="../assets/images/product-20-400x400.jpg" alt="Dog leash">
        <div class="addToCart">
          <i class="fa-regular fa-square"></i>
          <h3>ADD TO CART?</h3>
        </div>
        <div class="addedToCart">
          <i class="fa-regular fa-square-check"></i>
          <h3>VIEW CART</h3>
        </div>
        <h3>Dog leash</h3>
        <h4>$25.00</h4>
      </div>
      <div class="card">
        <img src="../assets/images/product-16-400x400.jpg" alt="Animal transport cage">
        <div class="addToCart">
          <i class="fa-regular fa-square"></i>
          <h3>ADD TO CART?</h3>
        </div>
        <div class="addedToCart">
          <i class="fa-regular fa-square-check"></i>
          <h3>VIEW CART</h3>
        </div>
        <h3>Animal transport cage</h3>
        <h4><span>$35.00</span>$25.00</h4>
      </div>
      <div class="card">
        <img src="../assets/images/product-11-400x400.jpg" alt="Colorful cat leash">
        <div class="addToCart">
          <i class="fa-regular fa-square"></i>
          <h3>ADD TO CART?</h3>
        </div>
        <div class="addedToCart">
          <i class="fa-regular fa-square-check"></i>
          <h3>VIEW CART</h3>
        </div>
        <h3>Colorful cat leash</h3>
        <h4>$12.00</h4>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ProductsForSale'
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
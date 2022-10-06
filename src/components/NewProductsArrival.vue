<template>
  <div class="container">
    <div class="text">
      <h2>New products arrival</h2>
      <p>Latest products</p>
    </div>
    <div class="contenitorCards">
      <div class="card">
        <img src="../assets/images/product-8-500x500.jpg" alt="Bad">
        <h3>Colored pet bed</h3>
        <h4>$18.00 - $26.00</h4>
      </div>
      <div class="card">
        <img src="../assets/images/product-2-500x500.jpg" alt="Food">
        <h3>Colorful ball set</h3>
        <h4>$29.00</h4>
      </div>
      <div class="card">
        <img src="../assets/images/product-3-500x500.jpg" alt="Toys">
        <h3>Dog bone</h3>
        <h4><span>$29.00</span>$18.00</h4>
      </div>
      <div class="card">
        <img src="../assets/images/product-4-500x500.jpg" alt="Transport">
        <h3>Animal transport bag</h3>
        <h4>$29.00</h4>
      </div>
      <div class="card">
        <img src="../assets/images/product-5-500x500.jpg" alt="Transport">
        <h3>Animal transport cage</h3>
        <h4>$35.00</h4>
      </div>
      <div class="card">
        <img src="../assets/images/product-10-500x500.jpg" alt="Transport">
        <h3>Closable cat litter</h3>
        <h4>$16.00</h4>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'NewProductsArrival'
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
      margin: 18px 5px;
      width: calc(100vh / 3 - 10px);

      img {
        width: 100%;
      }

      h3{
        font-size: 0.9rem;
        padding: 8px 0;
      }

      h4{
        color: rgb(136, 136, 136);
        font-size: 0.75rem;

        span{
          font-size: 0.6rem;
          padding: 10px;
          text-decoration: line-through #000;
        }
      }
    }
  }
}
</style>
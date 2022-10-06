<template>
  <div class="container">
    <div class="text">
      <h2>New products arrival</h2>
      <p>Latest products</p>
    </div>
    <div class="contenitorCards">
      <div class="card">
        <img src="../assets/images/product-9-500x500.jpg" alt="Bad">
        <p>Bad (1)</p>
      </div>
      <div class="card">
        <img src="../assets/images/product-3-500x500.jpg" alt="Food">
        <p>Food (6)</p>
      </div>
      <div class="card">
        <img src="../assets/images/product-2-500x500.jpg" alt="Toys">
        <p>Toys (6)</p>
      </div>
      <div class="card">
        <img src="../assets/images/product-4-500x500.jpg" alt="Transport">
        <p>Transport (6)</p>
      </div>
      <div class="card">
        <img src="../assets/images/product-4-500x500.jpg" alt="Transport">
        <p>Transport (6)</p>
      </div>
      <div class="card">
        <img src="../assets/images/product-4-500x500.jpg" alt="Transport">
        <p>Transport (6)</p>
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
    margin-bottom: 50px;

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

    .card {
      margin: 5px;
      width: calc(100vh / 3 - 10px + 10%);
      height: calc(100vh / 3 - 10px + 10%);

      img {
        width: 100%;
        height: 100%;
      }

      p{
        margin: 20px 0;
      }
    }
  }
}
</style>
<template>
  <div class="container">
    <div class="cards">
      <div class="card">
        <h2>Kibble</h2>
        <h4>Dry dog food</h4>
        <img src="../assets/images/food-transparent-18-400x420.png" alt="">
        <input type="button" value="Shop dry food">
      </div>
      <div class="card">
        <h2>Moist</h2>
        <h4>Canned dog food</h4>
        <img src="../assets/images/food-transparent-17-400x420.png" alt="">
        <input type="button" value="Shop moist food">
      </div>
      <div class="card">
        <h2>Frozen</h2>
        <h4>Freeze-Dried dog food</h4>
        <img src="../assets/images/food-transparent-16-400x420.png" alt="">
        <input type="button" value="Shop frozen food">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'FoodShopArea'
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

      h2{
        font-size: 1.8rem;
      }

      h4{
        font-size: 0.85rem;
        color: #3d6f42;
        padding: 20px 0;
      }

      img{
        width: 60%;
        padding: 10px 0;
      }

      input{
        color: #fff;
        background-color: #3d6f42;
        border-radius: 25px;
        padding: 10px 20px;
        border: none;
      }
    }
  }
}
</style>
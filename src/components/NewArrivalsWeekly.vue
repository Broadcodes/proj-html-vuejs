<template>
  <div class="contenitor">
    <div class="areaElement">
      <img src="../assets/images/banner-3-2x-scaled.jpg" alt="image Animals">
      <div class="text">
        <h4>FIND THE BEST ANIMAL SUPPLIES</h4>
        <h2>New arrivals weekly</h2>
        <input type="button" value="Learn more about us" @click="setPage">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'NewArrivalsWeekly',
  methods: {
    setPage() {
      this.$emit('page', 'Shop');
    }
  }
}
</script>

<style lang="scss" scoped>
.contenitor {
  padding: 50px 10%;

  .areaElement {
    position: relative;

    img {
      width: 100%;
      height: 450px;
      object-fit: cover;
      filter: brightness(75%);
    }

    .text {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      color: #fff;
      text-align: center;

      h4 {
        font-size: 0.7rem;
        letter-spacing: 0.2rem;
        word-spacing: 0.3rem;
      }

      h2 {
        font-size: 3rem;
        margin: 30px 0;
      }

      input {
        padding: 10px 20px;
        color: #000;
        border-radius: 25px;
        border: none;
        cursor: pointer;

        &:hover {
          background-color: #3d6f42;
          color: #fff;
        }
      }
    }
  }

}
</style>
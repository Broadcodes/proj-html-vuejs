<template>
  <div class="container">
    <div class="dogs">
      <img src="../assets/images/banner-8-2x.jpg" alt="dog">
      <div class="text">
        <h4>FIND THE BEST ANIMAL SUPPLIES</h4>
        <h2>Popular accessories</h2>
        <input type="button" value="View all toys accessories" @click="setPage(); getValueItem('dogs', 'Toys')">
      </div>
    </div>
    <div class="cats">
      <img src="../assets/images/banner-9-2x.jpg" alt="cat">
      <div class="text">
        <h4>FIND THE BEST FOOD</h4>
        <h2>New food arrival</h2>
        <input type="button" value="View all food products" @click="setPage(); getValueItem('cats', 'Food')">
      </div>
    </div>
  </div>
</template>
  
<script>
export default {
  name: 'AreaDogsAndCats',
  methods: {
    setPage() {
      this.$emit('page', 'Shop');
    },
    getValueItem(animal, category) {
      let dataAnimalCategory = [animal, category];
      this.$emit('elementAnimalCategory', dataAnimalCategory);
    }
  }
}
</script>
  
<style lang="scss" scoped>
.container {
  margin: 70px 0 0;
  display: flex;
  height: 400px;

  .dogs,
  .cats {
    flex-basis: 50%;
    display: flex;
    text-align: center;
    position: relative;
    transition: transform .6s;


    &:hover {
      transform: scale(1.05);
      z-index: 5;
    }

    img {
      width: 100%;
      object-fit: cover;
      filter: brightness(80%);
    }

    .text {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      color: #fff;

      h4 {
        font-size: 0.65rem;
      }

      h2 {
        padding: 25px 0 35px;
      }

      input {
        padding: 10px 20px;
        border: none;
        border-radius: 25px;
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
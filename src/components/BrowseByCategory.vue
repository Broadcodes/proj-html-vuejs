<template>
  <div class="container" id="browseByCategory">
    <div class="text">
      <h2>Browse by category</h2>
      <p>Angue parus et, tincidunt condimentum mauris. At nibh retrum mi in. Nisi, vitae interdum eleifend dui,
        consequat nulla rhoncus dictum. Viverra.</p>
    </div>
    <div class="contenitorCards">
      <div class="card" v-for="item in getData()" :key="item.id">
        <img :src="item.img" :alt="item.name">
        <p>{{item.category}} ({{item.quantity}})</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BrowseByCategory',
  data() {
    return {
      arrData: [],
    }
  },
  props: {
    data: Array
  },
  methods: {
    getData() {
      let arr = [];

      this.data.forEach(element => {
        if (element.id === 9) {
          arr.push(element)
        }
        if (element.id === 5) {
          arr.push(element)
        }
        if (element.id === 4) {
          arr.push(element)
        }
        if (element.id === 6) {
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
    justify-content: center;
    width: 100%;

    .card {
      margin: 5px;
      width: calc(100vh / 4 - 10px + 10%);
      height: calc(100vh / 4 - 10px + 10%);

      img {
        width: 100%;
        height: 100%;
      }

      p {
        margin: 20px 0;
      }
    }
  }
}
</style>
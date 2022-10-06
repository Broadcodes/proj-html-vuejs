<template>
  <div class="container" id="reviews">
    <h2>Users testimonials</h2>
    <div class="cards">
      <div class="card" v-for="item in this.feedback" :key="item.id">
        <img :src="item.img" alt="item.name">
        <h4>{{item.text}}</h4>
        <h4>{{item.name}}, {{item.company}}</h4>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'FeedbackUsers',
  props:{
    feedback: Array
  }
}
</script>

<style lang="scss" scoped>
.container {
  margin: 70px 0% 20px;
  background-color: #1e3120;
  background-image: url('@/assets/images/bg-transparent-3.png');
  background-size: 15%;
  text-align: center;
  color: #fff;
  padding: 80px 0 100px;

  .cards {
    margin: 30px 10%;

    display: flex;
    justify-content: space-between;

    .card {
      width: calc(100% / 3 - 30px);

      img {
        width: 65px;
        height: 65px;
        border-radius: 50px;
      }

      h4 {
        padding: 10px;
        font-size: 0.8rem;
        line-height: 1.3rem;
        color: #fff;
        font-weight: 400;
      }

      h4:nth-child(3){
        color: rgb(200, 200, 200);
      }
    }
  }
}
</style>
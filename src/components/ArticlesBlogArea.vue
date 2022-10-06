<template>
  <div class="contenitor">
    <div class="text">
      <h2>Get the best tips & tricks</h2>
      <h4>Recent articles</h4>
    </div>
    <div class="cards">
      <div class="card">
        <img src="../assets/images/blog-1-400x400.jpg" alt="blog-1">
        <div class="textHover">
          <h3>How to 'loose leash walk' your dog</h3>
          <h4>Tips & Tricks</h4>
        </div>
        <div class="textCard">
          <h3>How to 'loose leash walk' your dog</h3>
          <h4>April 21st, 2020</h4>
        </div>
      </div>
      <div class="card">
        <img src="../assets/images/blog-2-400x400.jpg" alt="blog-2">
        <div class="textHover">
          <h3>Stop cats from scratching furniture</h3>
          <h4>Tips & Tricks</h4>
        </div>
        <div class="textCard">
          <h3>Stop cats from scratching furniture</h3>
          <h4>April 19th, 2020</h4>
        </div>
      </div>
      <div class="card">
        <img src="../assets/images/blog-3-400x400.jpg" alt="blog-3">
        <div class="textHover">
          <h3>Where to buy the best pet food</h3>
          <h4>Tips & Tricks</h4>
        </div>
        <div class="textCard">
          <h3>Where to buy the best pet food</h3>
          <h4>April 16th, 2020</h4>
        </div>
      </div>
      <div class="card">
        <img src="../assets/images/blog-4-400x400.jpg" alt="blog-4">
        <div class="textHover">
          <h3>Proper care for your pet toys</h3>
          <h4>Tips & Tricks</h4>
        </div>
        <div class="textCard">
          <h3>Proper care for your pet toys</h3>
          <h4>April 17th, 2020</h4>
        </div>
      </div>
    </div>
    <input type="button" value="Read all articles">
  </div>
</template>

<script>
export default {
  name: 'ArticlesBlogArea'
}
</script>

<style lang="scss" scoped>
.contenitor {
  margin: 0px 10%;
  text-align: center;

  .text {
    h4 {
      font-size: 0.8rem;
      color: rgb(93, 93, 93);
      padding: 15px 0 40px;
    }
  }

  .cards {
    display: flex;
    justify-content: space-between;

    .card {
      width: calc(100% / 4 - 20px);
      position: relative;

      .textHover{
        display: none;
      }

      &:hover .textHover{
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        position: absolute;
        top: 0%;
        left: 0%;
        width: 100%;
        height: 100%;
        color: #fff;
        padding: 25px;

        h3{
          font-size: 1.3rem;
          transform: translateY(-50px);
          font-size: 1.2rem;
        }

        h4{
          transform: translateY(-50px);
          padding: 10px;
          font-size: 0.75rem;
        }
      }

      &:hover img{
        filter: sepia(20%) brightness(85%);
      }

      img {
        width: 100%;
      }

      .textCard {
        padding: 20px;
        text-align: left;

        h3 {
          font-size: 0.9rem;
          line-height: 1.4rem;
          font-weight: 300;
        }

        h4 {
          font-size: 0.6rem;
          padding: 5px 0;
          font-weight: 300;
        }
      }
    }
  }

  input {
    margin-top: 20px;
    padding: 10px 20px;
    border: none;
    border-radius: 25px;
    color: #fff;
    background-color: #3d6f42;
    cursor: pointer;

    &:hover {
      background-color: #529258;
      color: #fff;
    }
  }
}
</style>
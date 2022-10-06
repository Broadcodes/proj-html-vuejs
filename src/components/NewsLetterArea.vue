<template>
  <div class="container">
    <div class="boxNewsletter">
      <div class="text">
        <h2>Join our newsletter</h2>
        <h3>Libero dolores deleniti exercitationem tempore ab accusantium totam
          temporibus sit quae, quidem illum.
        </h3>
        <div class="submit">
          <input type="email" name="email" id="email" placeholder="Insert your email ...*">
          <input type="submit" value="Subscribe">
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'NewsLetterArea'
}
</script>

<style lang="scss" scoped>
.container {
  position: relative;
  top: -85px;
  margin: auto 10%;

  .boxNewsletter {
    background-image: url('@/assets/images/banner-7-2x-scaled.jpg');
    background-size: 100%;
    background-repeat: no-repeat;
    box-shadow: inset -60px -60px 100px rgba(176, 176, 176, 0.35);
    object-fit: cover;
    padding: 100px 80px;

    .text {
      width: 50%;

      h2 {
        font-size: 1.7rem;
      }

      h3 {
        font-size: 0.75rem;
        line-height: 1.3rem;
        padding: 20px 0 40px;
      }

      .submit {
        display: flex;

        input {
          border-radius: 25px;
          padding: 10px 20px;
          border: none;
        }

        input:nth-child(1) {
          background-color: #f8f5f2;
          width: 100%;
          margin-right: 20px;
        }

        input:nth-child(2) {
          background-color: #3d6f42;
          color: #fff;
          padding-left: 30px;
          padding-right: 30px;
          cursor: pointer;

          &:hover {
            background-color: #529258;
            color: #fff;
          }
        }
      }


    }
  }
}
</style>
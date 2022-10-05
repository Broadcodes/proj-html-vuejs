<template>
  <div class="container">
    <div class="areaFooterTop">
      <div class="areaInfoLink">
        <div class="companyInfo">
          <div class="logoAndTitle">
            <img src="@/assets/images/logo-symbol.png" alt="logo">
            <h2>Avada Pet Supplies</h2>
          </div>
          <ul>
            <li>1234 Avada Avenue Avadaville</li>
            <li>info@your-company.com</li>
            <li>Call us: (1) 234 5678</li>
          </ul>
        </div>
        <div class="areaLinks">
          <div class="links">
            <h2>Shop by brand</h2>
            <ul>
              <li>Bed</li>
              <li>Food</li>
              <li>Toys</li>
              <li>Transport</li>
            </ul>
          </div>
          <div class="links">
            <h2>Useful links</h2>
            <ul>
              <li>My account</li>
              <li>Orders</li>
              <li>Checkout</li>
              <li>Cart</li>
            </ul>
          </div>
        </div>
      </div>
      <div class="subscribe">
        <h3>Subscribe to our newsletter</h3>
        <input type="text" name="email" id="email" placeholder="Insert your email ...*">
        <input type="submit" value="Subscribe">
      </div>
    </div>
    <div class="areaFooterBottom">
      <ul>
        <li>Home</li>
        <li>About</li>
        <li>Blog</li>
        <li>Contact</li>
        <li>Shop</li>
      </ul>
      <ul>
        <li><i class="fa-brands fa-facebook-f"></i></li>
        <li><i class="fa-brands fa-twitter"></i></li>
        <li><i class="fa-brands fa-instagram"></i></li>
        <li><i class="fa-brands fa-youtube"></i></li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'FooterComponent'
}
</script>

<style lang="scss" scoped>
.container {
  width: 100%;
  padding: 80px 10%;
  color: #fff;
  background-color: #1e3120;
  cursor: default;

  .areaFooterTop {
    display: flex;
    padding-bottom: 50px;
    border-bottom: 1px solid rgb(70, 70, 70);

    .areaInfoLink {
      flex-basis: 80%;
      display: flex;

      .companyInfo {
        flex-basis: calc(100% / 2.5);
        padding-right: 20px;

        .logoAndTitle {
          display: flex;
          align-items: center;

          img {
            filter: invert(100%);
            margin-right: 10px;
            width: 45px;
          }

          h2 {
            font-size: 1.3rem;
          }
        }

        ul {
          list-style-type: none;
          margin-top: 30px;
          margin-left: 5px;

          li{
            font-size: 0.8rem;
            padding: 3px 0;
          }
        }
      }

      .areaLinks {
        display: flex;
        flex-grow: 1;

        .links{
          flex-basis: 50%;

          h2{
            font-size: 1.1rem;
          }

          ul {
          list-style-type: none;
          margin-top: 20px;

          li{
            font-size: 0.8rem;
            padding: 10px 0;
          }
        }
        }
      }
    }

    .subscribe {
      display: flex;
      flex-direction: column;
      justify-content: center;
      flex-grow: 1;
      max-width: 250px;
      height: 250px;
      padding: 30px;
      background-color: #264229;
      background-image: url("@/assets/images/bg-transparent-3.png");
      background-size: 100%;

      input{
        height: 45px;
        border-radius: 25px;
        margin: 15px 0;
        text-align: center;
      }

      input:nth-child(3){
        color: #fff;
        border: none;
        background-color: #3d6f42;
        cursor: pointer;
      }
    }
  }

  .areaFooterBottom {
    padding-top: 30px;

    ul {
      display: flex;
      justify-content: center;

      li {
        margin: 0 20px;
        list-style-type: none;
        padding: 20px 0;
        cursor: pointer;
      }
    }

  }






}
</style>
<template>
  <div>
    <div class="container">
      <div class="areaFooterTop">
        <div class="areaInfoLink">
          <div class="companyInfo">
            <div class="logoAndTitle">
              <img src="@/assets/images/mobile-light-pet-logo-2x-200x52.png" alt="logo">
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
                <li><a href="#">Bed</a></li>
                <li><a href="#">Food</a></li>
                <li><a href="#">Toys</a></li>
                <li><a href="#">Transport</a></li>
              </ul>
            </div>
            <div class="links">
              <h2>Useful links</h2>
              <ul>
                <li><a href="#">My account</a></li>
                <li><a href="#">Orders</a></li>
                <li><a href="#">Checkout</a></li>
                <li><a href="#">Cart</a></li>
              </ul>
            </div>
          </div>
        </div>
        <div class="subscribe">
          <h3>Subscribe to our newsletter</h3>
          <input type="email" name="email" id="email" placeholder="Insert your email ...*">
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
    <div class="copyright">
      <h3>&copy; Copyright 2012 - 2020 | Avada Theme by ThemeFusion | All Rights Reserved | Powered by WordPress</h3>
      <a href="../components/HeaderAreaTop.vue/#topHeader"><span><i class="fa-solid fa-chevron-up"></i></span></a>
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
  padding: 80px 10% 60px;
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
            margin-right: 10px;
          }
        }

        ul {
          list-style-type: none;
          margin-top: 30px;
          margin-left: 5px;

          li {
            font-size: 0.8rem;
            padding: 3px 0;
          }
        }
      }

      .areaLinks {
        display: flex;
        flex-grow: 1;

        .links {
          flex-basis: 50%;

          h2 {
            font-size: 1.1rem;
          }

          ul {
            list-style-type: none;
            margin-top: 20px;

            li {
              font-size: 0.8rem;
              padding: 10px 0;

              a {
                color: #fff;
                text-decoration: none;

                &:hover {
                  text-decoration: underline;
                }
              }
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

      input {
        height: 45px;
        border-radius: 25px;
        margin: 15px 0;
        text-align: center;
      }

      input:nth-child(3) {
        color: #fff;
        border: none;
        background-color: #3d6f42;
        cursor: pointer;

        &:hover {
          background-color: #529258;
          color: #fff;
        }
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

.copyright {
  width: 100%;
  height: 55px;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #000;
  position: relative;
  cursor: default;

  h3 {
    font-size: 0.7rem;
    color: #fff;
    font-weight: 300;
  }

  span {
    position: absolute;
    bottom: 0;
    right: 5%;
    width: 35px;
    height: 25px;
    border-top-left-radius: 5px;
    border-top-right-radius: 5px;
    background-color: rgb(69, 69, 69);
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: pointer;

    i {
      font-size: 0.7rem;
      color: #fff;
    }
  }
}
</style>
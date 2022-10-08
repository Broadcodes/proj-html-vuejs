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
                <!-- Mostra le categorie presenti nella sezione shop [food, transport, toys, bad] -->
                <li v-for="item in this.getCategory()" :key="item.category">
                  <p @click="setPage('Shop')">{{item}}</p>
                </li>
              </ul>
            </div>
            <div class="links">
              <h2>Useful links</h2>
              <ul>
                <li>
                  <p>My account</p>
                </li>
                <li>
                  <p>Orders</p>
                </li>
                <li>
                  <p>Checkout</p>
                </li>
                <li>
                  <p>Cart</p>
                </li>
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
          <!-- Visualizza la pagina cliccata -->
          <li @click="setPage('Home')"><a href="#">Home</a></li>
          <li @click="setPage('About')"><a href="#">About</a></li>
          <li @click="setPage('Blog')"><a href="#">Blog</a></li>
          <li @click="setPage('Contact')"><a href="#">Contact</a></li>
          <li @click="setPage('Shop')"><a href="#">Shop</a></li>
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
  name: 'FooterComponent',
  props: {
    dataShop: Array
  },
  methods: {
    getCategory() {
      let arr = [];

      this.dataShop.forEach(element => {
        arr.push(element.category)
      });

      return arr.filter((x, i) =>
        arr.indexOf(x) === i
      );
    },
    setPage(value) {
      this.$emit('page', value);
    }
  }
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

              p {
                color: #fff;
                cursor: pointer;
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

        a{
          color: #fff;
          text-decoration: none;

          &:hover{
            color: rgb(38, 116, 56);
          }
        }
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
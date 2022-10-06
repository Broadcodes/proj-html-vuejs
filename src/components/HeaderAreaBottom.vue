<template>
  <div class="navBar">

    <ul>
      <li @mouseenter="getShowMenu('home')" @mouseleave="getShowMenu('home')">Home <i class="fa-solid fa-chevron-down"></i>
        <ul :class="{listHome : listHome}">
          <li><a href="../components/BrowseByCategory.vue/#browseByCategory">Browse by category</a></li>
          <li><a href="../components/FoodShopArea.vue/#kindsOfFood">Kinds of food</a></li>
          <li><a href="../components/FeedbackUsers.vue/#reviews">Reviews</a></li>
          <li><a href="../components/NewProductsArrival.vue/#newProductsArrival">New products arrival</a></li>
        </ul>
      </li>
      <li @mouseenter="getShowMenu('shop')" @mouseleave="getShowMenu('shop')">Shop <i class="fa-solid fa-chevron-down"></i>
        <ul :class="{listShop : listShop}">
          <li @mouseenter="getShowMenu('dogs')" @mouseleave="getShowMenu('dogs')"><i class="fa-solid fa-bone"></i>Dogs<i class="fa-solid fa-chevron-down"></i>
            <ul :class="{categoryDogs : categoryDogs}">
              <li v-for="item in this.getCategory()" :key="item.id">{{item}}</li>
            </ul>
          </li>
          <li @mouseenter="getShowMenu('cats')" @mouseleave="getShowMenu('cats')"><i class="fa-solid fa-paw"></i>Cats<i class="fa-solid fa-chevron-down"></i>
            <ul :class="{categoryCats : categoryCats}">
              <li v-for="item in this.getCategory()" :key="item.id">{{item}}</li>
            </ul>
          </li>
        </ul>
      </li>
      <li>About</li>
      <li>Blog</li>
      <li>Contact</li>
      <li @mouseenter="getShowMenu('brand')" @mouseleave="getShowMenu('brand')">Shop by brand <span><i class="fa-solid fa-chevron-down"></i></span>
        <ul :class="{listBrand : listBrand}">
          <li v-for="item in this.getBrand()" :key="item.id">{{item}}</li>
        </ul>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HeaderAreaBottom',
  data(){
    return{
      listHome: false,
      listShop: false,
      categoryDogs: false,
      categoryCats: false,
      listBrand: false,
    }
  },
  props: {
    menu: Array,
  },
  methods: {
    getCategory() {
      let arr = [];

      this.menu.forEach(element => {
        arr.push(element.category)
      });

      return arr.filter((x, i) =>
        arr.indexOf(x) === i
      );
    },
    getBrand() {
      let arr = [];

      this.menu.forEach(element => {
        arr.push(element.brand)
      });

      return arr.filter((x, i) =>
        arr.indexOf(x) === i
      );
    },
    getShowMenu(value){

      switch (value) {
        case 'home':
          if(this.listHome === false){
            this.listHome = true;
          } else {
            this.listHome = false;
          }
          break;
        case 'shop':
          if(this.listShop === false){
            this.listShop = true;
          } else {
            this.listShop = false;
          }
          break;
        case 'dogs':
          if(this.categoryDogs === false){
            this.categoryDogs = true;
          } else {
            this.categoryDogs = false;
          }
          break;
        case 'cats':
          if(this.categoryCats === false){
            this.categoryCats = true;
          } else {
            this.categoryCats = false;
          }
          break;
        case 'brand':
          if(this.listBrand === false){
            this.listBrand = true;
          } else {
            this.listBrand = false;
          }
          break;
      
        default:
          break;
      }
    }
  }
}
</script>

<style lang="scss" scoped>
.navBar {
  color: rgb(87, 87, 87);

  i {
    font-size: 0.7rem;
  }

  .showMenu {
    display: block !important;
  }

  // Menu principale [Menu - Shop - About - Blog - Contact - Shop by brand]
  &>ul {
    display: flex;
    justify-content: center;

    &>li {
      display: flex;
      align-items: center;
      margin: 0 20px;
      list-style-type: none;
      position: relative;
      cursor: pointer;
      height: 50px;

      a {
        padding: 5px 0;
        text-decoration: none;
        color: #000;
      }

      i {
        padding: 5px
      }

      // Menu secondario: Aree in grigio scuro
      &>ul {
        border-radius: 10px;
        background-color: rgb(237, 237, 237);
        padding: 5px;
        list-style-type: none;
        position: absolute;
        top: 50px;
        z-index: 100;
        left: 0px;
        width: 25vh;
        display: none;

        li {
          border-radius: 5px;
          padding: 6px;
          font-size: 0.9rem;

          // Sottocategorie del Dogs e del Cats
          ul {
            list-style-type: none;
            display: none;
            margin-top: 10px;

            li {
              margin-left: 30px;

              &:hover {
                background-color: rgb(237, 237, 237);
              }
            }
          }

          &:hover {
            background-color: rgb(246, 246, 246);

          }
        }
      }

      .listShop li {
        &:hover{
          background-color: rgb(237, 237, 237);
        }

        ul>li:hover {
          background-color: rgb(246, 246, 246);
        }
      }

      .listShop li i {
        margin: 0 10px;
      }

      .listHome,
      .listShop,
      .categoryDogs,
      .categoryCats,
      .listBrand{
        display: block;
      }

    }
  }
}
</style>
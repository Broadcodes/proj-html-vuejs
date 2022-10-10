<template>
  <div class="navBar">
    <ul>
      <!-- Il getShowMenu verifica quale tendina del menu deve essere aperta, passando la stringa dell'elemento
           selezionato mostra i dati presenti al suo interno -->

      <!-- Il metodo setEmitToHome, invece, permette di mostrare l'intera pagina cliccata-->
      <li @mouseenter="getShowMenu('home')" @mouseleave="getShowMenu('home')" @click="setEmitToHome('Home'); $emit('showCart', false)">
        <a href="#" :class="{active : setNewPageActive() === 'Home'}"> Home </a><i class="fa-solid fa-chevron-down"></i>
        <ul :class="{listHome : listHome}">

          <!-- Nell'href passo l'indirizzo a cui si deve agganciare il sottoelemento cliccato dall'utente;
               ad esempio: se si va con il cursore su Home e si clicca su review, il contenuto mostrerà
               la sezione delle recensioni e non l'intera pagina della home -->
          <li @click="setEmitToHome('Home')"><a href="../components/BrowseByCategory.vue/#browseByCategory">Browse by
              category</a></li>
          <li @click="setEmitToHome('Home')"><a href="../components/FoodShopArea.vue/#kindsOfFood">Kinds of food</a>
          </li>
          <li @click="setEmitToHome('Home')"><a href="../components/FeedbackUsers.vue/#reviews">Reviews</a></li>
          <li @click="setEmitToHome('Home')"><a href="../components/NewProductsArrival.vue/#newProductsArrival">New
              products arrival</a></li>
        </ul>
      </li>
      <li @mouseenter="getShowMenu('shop')" @mouseleave="getShowMenu('shop')" @click="setEmitToHome('Shop'); $emit('showCart', false)">
        <!-- getValueItem ha valore di string vuota per gestire il caso in cui l'utente clicca direttamente su Shop e non
             una sottocategoria -->
        <a href="#" @click="getValueItem('', '')" :class="{active : setNewPageActive() === 'Shop'}">Shop</a> <i
          class="fa-solid fa-chevron-down"></i>
        <ul :class="{listShop : listShop}">
          <li @mouseenter="getShowMenu('dogs')" @mouseleave="getShowMenu('dogs')"><i class="fa-solid fa-bone"></i>Dogs<i
              class="fa-solid fa-chevron-down"></i>
            <ul :class="{categoryDogs : categoryDogs}">
              <!-- Il metodo getValueItem permette mediante passaggio di "animale" e "categoria" (ad es. cats - food, dogs - transport, ecc) 
                   la visualizzazione delle sottocategorie; ad es: se l'utente clicca su toys nell'area dedicata ai gatti,
                   verranno mostrati solo i giochi relativi ai gatti -->
              <li v-for="item in this.getCategory()" :key="item.id" @click="getValueItem('dogs', item)"><a
                  href="#">{{item}}</a></li>
            </ul>
          </li>
          <li @mouseenter="getShowMenu('cats')" @mouseleave="getShowMenu('cats')"><i class="fa-solid fa-paw"></i>Cats<i
              class="fa-solid fa-chevron-down"></i>
            <ul :class="{categoryCats : categoryCats}">
              <li v-for="item in this.getCategory()" :key="item.id" @click="getValueItem('cats', item)"><a
                  href="#">{{item}}</a></li>
            </ul>
          </li>
        </ul>
      </li>
      <li @click="setEmitToHome('About'); $emit('showCart', false)"><a href="#" :class="{active : setNewPageActive() === 'About'}">About</a></li>
      <li @click="setEmitToHome('Blog'); $emit('showCart', false)"><a href="#" :class="{active : setNewPageActive() === 'Blog'}">Blog</a></li>
      <li @click="setEmitToHome('Contact'); $emit('showCart', false)"><a href="#" :class="{active : setNewPageActive() === 'Contact'}">Contact</a>
      </li>
      <li @mouseenter="getShowMenu('brand')" @mouseleave="getShowMenu('brand')" @click="setEmitToHome('Brand'); $emit('showCart', false)">
        <a href="#" :class="{active : setNewPageActive() === 'Brand'}">Shop by brand</a> <span><i
            class="fa-solid fa-chevron-down"></i></span>
        <ul :class="{listBrand : listBrand}">
          <li v-for="item in this.getBrand()" :key="item.id" @click="elementSelected(item)">{{item}}</li>
        </ul>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HeaderAreaBottom',
  data() {
    return {
      listHome: false,
      listShop: false,
      categoryDogs: false,
      categoryCats: false,
      listBrand: false,
      page: 'Home'
    }
  },
  props: {
    menu: Array,
    pageActive: String
  },
  methods: {
    setNewPageActive() {

      if (this.pageActive !== '') {
        this.page = this.pageActive;
      }

      return this.page;
    },
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
    getShowMenu(value) {

      switch (value) {
        case 'home':
          if (this.listHome === false) {
            this.listHome = true;
          } else {
            this.listHome = false;
          }
          break;
        case 'shop':
          if (this.listShop === false) {
            this.listShop = true;
          } else {
            this.listShop = false;
          }
          break;
        case 'dogs':
          if (this.categoryDogs === false) {
            this.categoryDogs = true;
          } else {
            this.categoryDogs = false;
          }
          break;
        case 'cats':
          if (this.categoryCats === false) {
            this.categoryCats = true;
          } else {
            this.categoryCats = false;
          }
          break;
        case 'brand':
          if (this.listBrand === false) {
            this.listBrand = true;
          } else {
            this.listBrand = false;
          }
          break;

        default:
          break;
      }
    },
    setEmitToHome(value) {
      this.page = value;
      this.$emit('pageSelected', value);
    },
    elementSelected(value) {
      this.$emit('elementMenuSelected', value);
    },
    getValueItem(animal, category) {
      let dataAnimalCategory = [animal, category];
      this.$emit('elementAnimalCategory', dataAnimalCategory);
    }
  }
}
</script>

<style lang="scss" scoped>
.navBar {
  color: rgb(87, 87, 87);
  background-color: rgba(255, 255, 255, 0.3);

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

    &>li a.active {
      color: #3d6f42;
      font-weight: 600;
    }

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
        font-weight: 300;
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
          color: #000;
          font-weight: 300;

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
        &:hover {
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
      .listBrand {
        display: block;
      }

    }
  }
}
</style>
<template>
  <div class="navBar">
    <ul>
      <li>Home <i class="fa-solid fa-chevron-down"></i>
        <ul id="listHome">
          <li>Browse by category</li>
          <li>Kinds of food</li>
          <li>Reviews</li>
          <li>New products arrival</li>
        </ul>
      </li>
      <li>Shop <i class="fa-solid fa-chevron-down"></i>
        <ul id="listShop">
          <li><i class="fa-solid fa-bone"></i>Dogs<i class="fa-solid fa-chevron-down"></i>
            <ul id="categoryDogs">
              <li>Bed</li>
              <li>Food</li>
              <li>Toys</li>
              <li>Transport</li>
            </ul>
          </li>
          <li><i class="fa-solid fa-paw"></i>Cats<i class="fa-solid fa-chevron-down"></i>
            <ul id="categoryCats">
              <li>Bed</li>
              <li>Food</li>
              <li>Toys</li>
              <li>Transport</li>
            </ul>
          </li>
        </ul>
      </li>
      <li>About</li>
      <li>Blog</li>
      <li>Contact</li>
      <li>Shop by brand <span><i class="fa-solid fa-chevron-down"></i></span>
        <ul id="listBrand">
          <li>Bed</li>
          <li>Food</li>
          <li>Toys</li>
          <li>Transport</li>
        </ul>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HeaderAreaBottom'
}
</script>

<style lang="scss" scoped>
.navBar {
  padding: 20px;
  color: rgb(87, 87, 87);
  cursor: pointer;

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
      margin: 0 20px;
      list-style-type: none;
      position: relative;

      // Menu secondario: Aree in grigio scuro
      &>ul {
        margin-top: 10px;
        border-radius: 10px;
        background-color: rgb(237, 237, 237);
        padding: 5px;
        list-style-type: none;
        position: absolute;
        left: 0px;
        width: 15vw;
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

      #listShop li i {
        margin: 0 10px;
      }

      // #listHome,
      // #listShop,
      // #listBrand,
      // #categoryDogs,
      // #categoryCats {
      //   display: block;
      // }

    }
  }
}
</style>
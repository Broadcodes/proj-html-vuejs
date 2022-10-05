<template>
  <div class="navBar">
    <ul class="firstMenu">
      <li>home <i class="fa-solid fa-chevron-down"></i>
        <ul class="secondMenu">
          <li>Browse by category</li>
          <li>Kinds of food</li>
          <li>Reviews</li>
          <li>New products arrival</li>
        </ul>
      </li>
      <li>Shop <i class="fa-solid fa-chevron-down"></i>
        <ul class="secondMenu">
          <li><i class="fa-solid fa-bone"></i>Dogs<i class="fa-solid fa-chevron-right"></i>
            <ul class="thirdMenu">
              <li>Bed</li>
              <li>Food</li>
              <li>Toys</li>
              <li>Transport</li>
            </ul>
          </li>
          <li><i class="fa-solid fa-paw"></i>Cats<i class="fa-solid fa-chevron-right"></i>
            <ul class="thirdMenu">
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
      <li>Shop by brand <span><i class="fa-solid fa-chevron-down"></i></span></li>
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

  .firstMenu {
    display: flex;
    justify-content: center;
    align-items: center;

    li {
      margin: 0 20px;
      list-style-type: none;
    }
  }

}
</style>
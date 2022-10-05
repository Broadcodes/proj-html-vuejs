<template>
    <div class="container">
        <div class="logo">
            <img src="@/assets/img/logo.png" alt="logo">
            <p>Avada Pet Supplies</p>
        </div>
        <div class="areaSearch">
            <i class="fa-solid fa-magnifying-glass"></i>
            <input type="text" id="searchInput">
        </div>
        <p><span>Questions?</span>Call us: 1.800.123.4567</p>
        <div class="areaIconShopAccount">
            <i class="fa-solid fa-bag-shopping"></i>
            <i class="fa-regular fa-user"></i>
        </div>
    </div>
</template>

<script>
export default {
    name: 'HeaderAreaTop'
}
</script>

<style lang="scss" scoped>
.container {
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-bottom: 1px solid #000;

    .logo {
        display: flex;
        justify-content: center;
        align-items: center;
    }
}
</style>
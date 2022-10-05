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
    border-bottom: 1px solid #eaeaea;
    padding: 10px 10%;

    .logo {
        display: flex;
        justify-content: center;
        align-items: center;

        img{
            margin-right: 10px;
        }
        
        p{
            font-weight: 600;
        }
    }

    .areaSearch{
        background-color: #f3f4f3;
        border-radius: 20px;
        width: 23%;
        padding: 5px 10px;

        input{
            width: calc(100% - 15%);
            height: 25px;
            border: none;
            background-color: #f3f4f3;
            margin-left: 5px;
            outline: none;
        }

        i{
            font-size: 0.8rem;
            margin: 0 5px;
        }
    }

    & > p{
        span{
            font-weight: 600;
            padding: 0 5px;
        }
    }

    .areaIconShopAccount{
        i{
            margin: 5px;
            padding: 5px;
            cursor: pointer;
        }
    }
}
</style>
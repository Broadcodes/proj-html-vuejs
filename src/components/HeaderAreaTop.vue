<template>
    <div class="container" id="topHeader">
        <div class="logo" @click="showCart(false)">
            <img src="@/assets/images/dark-pet-logo.png" alt="logo" @click="$emit('pageHome', 'Home')">
        </div>
        <div class="areaSearch">
            <i class="fa-solid fa-magnifying-glass"></i>
            <input type="text" id="searchInput" v-model="textSearch" @keyup="getSearch(textSearch)">
        </div>
        <p><span>Questions?</span>Call us: 1.800.123.4567</p>
        <div class="areaIconShopAccount">
            <i class="fa-solid fa-bag-shopping" @click="showCart">
                <span v-if="this.numProducts !== 0">
                    {{this.numProducts}}
                </span>
            </i>
            <i class="fa-regular fa-user"></i>
        </div>
    </div>
</template>

<script>
export default {
    name: "HeaderAreaTop",
    data() {
        return {
            textSearch: "",
            valueShowCart: false
        };
    },
    methods: {
        getSearch(value) {
            this.$emit("searchInput", value);
        },
        showCart(value) {
            if (this.valueShowCart) {
                this.valueShowCart = false;
                value = false;
            }
            else {
                this.valueShowCart = true;
                value = true;
            }
            
            this.$emit("showCart", value);
        }
    },
    props: {
        numProducts: Number
    }
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
        justify-content: left;
        align-items: center;
        cursor: pointer;

        img {
            width: 80%;
            margin-right: 10px;
        }
    }

    .areaSearch {
        background-color: #f3f4f3;
        border-radius: 20px;
        width: 23%;
        padding: 5px 10px;

        input {
            width: calc(100% - 15%);
            height: 25px;
            border: none;
            background-color: #f3f4f3;
            margin-left: 5px;
            outline: none;
        }

        i {
            font-size: 0.8rem;
            margin: 0 5px;
        }
    }

    &>p {
        span {
            font-weight: 600;
            padding: 0 5px;
        }
    }

    .areaIconShopAccount {
        i {
            margin: 5px;
            padding: 5px;
            cursor: pointer;
            position: relative;

            span{
                position: absolute;
                top: 15px;
                left: 12px;
                background-color: red;
                display: flex;
                justify-content: center;
                align-items: center;
                width: 15px;
                height: 15px;
                border-radius: 50px;
                font-size: 0.6rem;
                color: #fff;
            }
        }
    }
}
</style>
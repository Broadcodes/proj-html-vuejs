<template>
    <div class="container">
        <div class="text">
            <h4>FIND THE BEST ANIMAL SUPPLIES</h4>
            <h2>We know animals are a part of your family, let us help take care of them.</h2>
            <input type="button" value="Learn more about us">
        </div>
        <div class="iconMessage">
            <span><img src="../assets/images/demos.png" alt="demos"></span>
            <span><img src="../assets/images/OnSale.png" alt="On Sale"></span>
        </div>
    </div>
</template>

<script>
export default {
    name: 'JumboTronArea'
}
</script>

<style lang="scss" scoped>
.container {
    width: 100%;
    height: 550px;
    background-image: url('@/assets/images/banner-5-2x-scaled.jpg');
    background-size: cover;
    position: relative;

    .text {
        position: absolute;
        top: 50%;
        transform: translateY(-50%);
        left: 10%;
        width: 35%;

        h4,
        h2 {
            color: #fff;
        }

        h4 {
            font-size: 0.7rem;
        }

        h2 {
            font-size: 2.3rem;
            line-height: 3rem;
            margin: 30px 0;
        }

        input {
            padding: 10px 25px;
            border-radius: 25px;
            border: none;
        }
    }

    .iconMessage {
        position: absolute;
        top: -45px;
        right: 5px;


        span {
            display: block;
            background-color: #fff;
            padding: 5px;
            border-radius: 5px;
            margin: 5px
        }
    }
}
</style>
<template>
    <div class="container">
        <h2>Buy our best products at a best price</h2>
        <div id="Food">
            <h2>FOOD</h2>
            <ul class="cards">
                <li v-for="food in this.getCategory('Food')" :key="food.id">
                    <div class="card">
                        <img :src="food.img" :alt="food.name">
                        <h2>{{food.name}}</h2>
                        <h3><span>Animal: </span> <span>{{food.animal}}</span></h3>
                        <h3><span>Quantity: </span> <span>{{food.quantity}}</span></h3>
                        <h3><span>Price: </span> <span>{{food.price}}</span></h3>
                        <input type="button" value="Add To Cart" @click="setQuantityCart()">
                    </div>
                </li>
            </ul>
        </div>
        <div id="Toys">
            <h2>TOYS</h2>
            <ul class="cards">
                <li v-for="food in this.getCategory('Toys')" :key="food.id">
                    <div class="card">
                        <img :src="food.img" :alt="food.name">
                        <h2>{{food.name}}</h2>
                        <h3><span>Animal: </span> <span>{{food.animal}}</span></h3>
                        <h3><span>Quantity: </span> <span>{{food.quantity}}</span></h3>
                        <h3><span>Price: </span> <span>{{food.price}}</span></h3>
                        <input type="button" value="Add To Cart" @click="setQuantityCart()">
                    </div>
                </li>
            </ul>
        </div>
        <div id="Transport">
            <h2>TRANSPORT</h2>
            <ul class="cards">
                <li v-for="food in this.getCategory('Transport')" :key="food.id">
                    <div class="card">
                        <img :src="food.img" :alt="food.name">
                        <h2>{{food.name}}</h2>
                        <h3><span>Animal: </span> <span>{{food.animal}}</span></h3>
                        <h3><span>Quantity: </span> <span>{{food.quantity}}</span></h3>
                        <h3><span>Price: </span> <span>{{food.price}}</span></h3>
                        <input type="button" value="Add To Cart" @click="setQuantityCart()">
                    </div>
                </li>
            </ul>
        </div>
        <div id="Bad">
            <h2>BAD</h2>
            <ul class="cards">
                <li v-for="food in this.getCategory('Bad')" :key="food.id">
                    <div class="card">
                        <img :src="food.img" :alt="food.name">
                        <h2>{{food.name}}</h2>
                        <h3><span>Animal: </span> <span>{{food.animal}}</span></h3>
                        <h3><span>Quantity: </span> <span>{{food.quantity}}</span></h3>
                        <h3><span>Price: </span> <span>{{food.price}}</span></h3>
                        <input type="button" value="Add To Cart" @click="setQuantityCart()">
                    </div>
                </li>
            </ul>
        </div>
        <div id="Dogs">
            <h2>DOGS</h2>
            <ul class="cards">
                <li v-for="food in this.getCategory('Dogs')" :key="food.id">
                    <div class="card">
                        <img :src="food.img" :alt="food.name">
                        <h2>{{food.name}}</h2>
                        <h3><span>Animal: </span> <span>{{food.animal}}</span></h3>
                        <h3><span>Quantity: </span> <span>{{food.quantity}}</span></h3>
                        <h3><span>Price: </span> <span>{{food.price}}</span></h3>
                        <input type="button" value="Add To Cart" @click="setQuantityCart()">
                    </div>
                </li>
            </ul>
        </div>
        <div id="Cats">
            <h2>CATS</h2>
            <ul class="cards">
                <li v-for="food in this.getCategory('Cats')" :key="food.id">
                    <div class="card">
                        <img :src="food.img" :alt="food.name">
                        <h2>{{food.name}}</h2>
                        <h3><span>Animal: </span> <span>{{food.animal}}</span></h3>
                        <h3><span>Quantity: </span> <span>{{food.quantity}}</span></h3>
                        <h3><span>Price: </span> <span>{{food.price}}</span></h3>
                        <input type="button" value="Add To Cart" @click="setQuantityCart()">
                    </div>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    name: 'ShopComponent',
    data(){
        return{
            quantity: 0
        }
    },
    props: {
        dataShop: Array
    },
    methods: {
        getCategory(typeCategory) {
            let arr = [];

            this.dataShop.forEach(element => {
                if (element.category === typeCategory || element.animal === typeCategory) {
                    arr.push(element);
                }
            });

            return arr;
        },
        setQuantityCart(){
            this.quantity = 0;
            this.$emit('cart', ++this.quantity);
        }
    }
}
</script>

<style lang="scss" scoped>
.container {
    margin: 50px 10%;

    &>h2 {
        font-size: 2.5rem;
        margin: 30px 0 60px;
    }

    &>div>h2 {
        font-size: 1.5rem;
        margin: 50px;
    }

    .cards {
        display: flex;
        list-style-type: none;
        width: 100%;
        flex-wrap: wrap;

        .card {
            display: flex;
            flex-direction: column;
            justify-content: space-around;
            column-gap: 20px;
            margin: 10px;
            max-width: 350px;
            padding: 50px;
            min-height: 570px;
            max-height: 570px;
            background-color: rgb(240, 234, 194);
            border-radius: 30px;

            img {
                width: 100%;
                max-width: 300px;
                border-radius: 50%;
                background-color: #f9f5f2;
            }

            h2 {
                padding: 20px 0;
            }

            h3 {
                padding: 5px 0px;

                span:nth-child(1) {
                    color: rgb(126, 45, 45);
                }
                
                span:nth-child(2) {
                    font-size: 1rem;
                    padding: 0 10px;
                }
            }

            input{
                padding: 10px 20px;
                background-color: #fff;
                border-radius: 25px;
                border: none;
                margin: 10px;
                cursor: pointer;

                &:hover{
                    background-color: #1e3120;
                    color: #fff;
                }
            }
        }
    }
}
</style>
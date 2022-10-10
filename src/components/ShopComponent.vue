<template>
    <div class="container">
        <h2>Buy our best products at a best price</h2>
        <!-- setAnimalCategory[1] è una array che contiene due valori ['tipo Animale', 'Categoria'].
             In questo caso si sta valutando se la categoria ha valore vuoto o meno. Nel caso il valore sia pari a vuoto
             viene mostrata l'intera pagina di shop, in caso contrario viene visualizzata SOLO la parte relativa alla categoria
             selezionata. Ad esempio: Se l'utente clicca su Cats e successivamente transport, verrà visualizzata solo quella sezione -->
        <div v-if="setAnimalCategory[1] === '' || this.setValuePage()">
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
                            <input type="button" value="Add To Cart" @click="setQuantityCart(food.id)">
                        </div>
                    </li>
                </ul>
            </div>
            <div id="Toys">
                <h2>TOYS</h2>
                <ul class="cards">
                    <li v-for="toys in this.getCategory('Toys')" :key="toys.id">
                        <div class="card">
                            <img :src="toys.img" :alt="toys.name">
                            <h2>{{toys.name}}</h2>
                            <h3><span>Animal: </span> <span>{{toys.animal}}</span></h3>
                            <h3><span>Quantity: </span> <span>{{toys.quantity}}</span></h3>
                            <h3><span>Price: </span> <span>{{toys.price}}</span></h3>
                            <input type="button" value="Add To Cart" @click="setQuantityCart(toys.id)">
                        </div>
                    </li>
                </ul>
            </div>
            <div id="Transport">
                <h2>TRANSPORT</h2>
                <ul class="cards">
                    <li v-for="transport in this.getCategory('Transport')" :key="transport.id">
                        <div class="card">
                            <img :src="transport.img" :alt="transport.name">
                            <h2>{{transport.name}}</h2>
                            <h3><span>Animal: </span> <span>{{transport.animal}}</span></h3>
                            <h3><span>Quantity: </span> <span>{{transport.quantity}}</span></h3>
                            <h3><span>Price: </span> <span>{{transport.price}}</span></h3>
                            <input type="button" value="Add To Cart" @click="setQuantityCart(transport.id)">
                        </div>
                    </li>
                </ul>
            </div>
            <div id="Bad">
                <h2>BAD</h2>
                <ul class="cards">
                    <li v-for="bad in this.getCategory('Bad')" :key="bad.id">
                        <div class="card">
                            <img :src="bad.img" :alt="bad.name">
                            <h2>{{bad.name}}</h2>
                            <h3><span>Animal: </span> <span>{{bad.animal}}</span></h3>
                            <h3><span>Quantity: </span> <span>{{bad.quantity}}</span></h3>
                            <h3><span>Price: </span> <span>{{bad.price}}</span></h3>
                            <input type="button" value="Add To Cart" @click="setQuantityCart(bad.id)">
                        </div>
                    </li>
                </ul>
            </div>
            <div id="Dogs">
                <h2>DOGS</h2>
                <ul class="cards">
                    <li v-for="dogs in this.getCategory('Dogs')" :key="dogs.id">
                        <div class="card">
                            <img :src="dogs.img" :alt="dogs.name">
                            <h2>{{dogs.name}}</h2>
                            <h3><span>Animal: </span> <span>{{dogs.animal}}</span></h3>
                            <h3><span>Quantity: </span> <span>{{dogs.quantity}}</span></h3>
                            <h3><span>Price: </span> <span>{{dogs.price}}</span></h3>
                            <input type="button" value="Add To Cart" @click="setQuantityCart(dogs.id)">
                        </div>
                    </li>
                </ul>
            </div>
            <div id="Cats">
                <h2>CATS</h2>
                <ul class="cards">
                    <li v-for="cats in this.getCategory('Cats')" :key="cats.id">
                        <div class="card">
                            <img :src="cats.img" :alt="cats.name">
                            <h2>{{cats.name}}</h2>
                            <h3><span>Animal: </span> <span>{{cats.animal}}</span></h3>
                            <h3><span>Quantity: </span> <span>{{cats.quantity}}</span></h3>
                            <h3><span>Price: </span> <span>{{cats.price}}</span></h3>
                            <input type="button" value="Add To Cart" @click="setQuantityCart(cats.id)">
                        </div>
                    </li>
                </ul>
            </div>
        </div>
        <div v-else>
            <ul class="cards">
                <li v-for="item in dataShop" :key="item.id">
                    <!-- Condizione necessaria per valutare quale categoria mostrare in base al tipo di animale selezionato -->
                    <div class="card"
                        v-if="item.animal.toLowerCase() === setAnimalCategory[0].toLowerCase() && item.category.toLowerCase() === setAnimalCategory[1].toLowerCase()">
                        <img :src=" item.img" :alt="item.name">
                        <h2>{{item.name}}</h2>
                        <h3><span>Animal: </span> <span>{{item.animal}}</span></h3>
                        <h3><span>Quantity: </span> <span>{{item.quantity}}</span></h3>
                        <h3><span>Price: </span> <span>{{item.price}}</span></h3>
                        <input type="button" value="Add To Cart" @click="setQuantityCart(item.id)">
                    </div>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
import { shop } from '@/data';
import { saveProducts } from '@/data';

export default {
    name: 'ShopComponent',
    data() {
        return {
            quantity: 0,
            animalCategory: [],
            shop,
            saveProducts
        }
    },
    props: {
        dataShop: Array,
        setAnimalCategory: Array,
        setPageShop: Boolean
    },
    methods: {
        setQuantityCart(id) {

            this.shop.forEach(item => {
                if (item.id === id) {
                    this.saveProducts.push(item);
                }
            });

            this.quantity = 0;
            this.$emit('cart', ++this.quantity);
        },
        getCategory(typeCategory) {
            let arr = [];

            this.dataShop.forEach(element => {
                if (element.category === typeCategory || element.animal === typeCategory) {
                    arr.push(element);
                }
            });

            return arr;
        },
        setValuePage() {
            if (this.setAnimalCategory[0] === '' && this.setAnimalCategory[1] === '' ||
                this.setAnimalCategory[0] === undefined && this.setAnimalCategory[1] === undefined) {
                console.log(this.setPageShop)
                return this.setPageShop;
            }

            return false;
        }
    },
    created() {
        window.scroll({
            top: 0,
            left: 0,
        });
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

            input {
                padding: 10px 20px;
                background-color: #fff;
                border-radius: 25px;
                border: none;
                margin: 10px;
                cursor: pointer;

                &:hover {
                    background-color: #1e3120;
                    color: #fff;
                }
            }
        }
    }
}
</style>
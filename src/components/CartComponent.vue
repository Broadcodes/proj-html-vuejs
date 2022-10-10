<template>
    <div class="container">
        <div class="areaData">
            <h2>Pay with</h2>
            <div class="payArea">
                <button><i class="fa-brands fa-google-pay"></i></button>
                <button><i class="fa-brands fa-paypal"></i></button>
                <button><i class="fa-brands fa-amazon-pay"></i></button>
            </div>
            <h4>OR</h4>
            <h3>Contact Information</h3>
            <input type="email" name="email" id="email" placeholder="Email">
            <div class="check">
                <input type="checkbox" name="newsAndOffers" id="newsAndOffers">
                <h5>Keep me up to date on news and exclusive offers</h5>
            </div>
            <h3>Shipping address</h3>
            <form method="post">
                <div class="name">
                    <input type="text" name="name" id="name" placeholder="First name" required>
                    <input type="text" name="surname" id="surname" placeholder="Last name" required>
                </div>
                <div class="elementForm">
                    <input type="text" name="company" id="company" placeholder="Company (option)">
                    <input type="text" name="address" id="address" placeholder="Address" required>
                    <input type="text" name="apartment" id="apartment" placeholder="Apartment, suite, stc. (option)">
                    <input type="text" name="city" id="city" placeholder="City" required>
                    <input type="text" name="country" id="country" placeholder="Country" required>
                    <input type="text" name="postalCode" id="postalCode" placeholder="Postal code" required>
                    <input type="text" name="phone" id="phone" placeholder="Phone (optional)">
                </div>

                <input type="submit" value="Buy" id="submit">
            </form>
        </div>
        <div class="areaSummary">
            <h3>Items in your cart:</h3>
            <div v-if="this.saveProducts.length > 0">
                <ul>
                    <li v-for="(item, index) in this.saveProducts" :key="index"><span>{{index + 1}} -
                            {{item.name}}</span><span>{{item.price}}</span></li>
                </ul>
                <h4>Total</h4>
                <h3>$ {{this.getTotalPrice()}}</h3>
            </div>
            <div v-else>
                <h5>No products added to the cart</h5>
            </div>
        </div>
    </div>
</template>

<script>
import { saveProducts } from '@/data.js'
export default {
    name: 'CartComponent',
    data() {
        return {
            saveProducts,
        }
    },
    methods: {
        getTotalPrice() {
            let price = 0

            this.saveProducts.forEach(element => {

                if(element.price.length > 10){

                    let firstPrice = parseFloat(element.price.substring(1, 6));
                    let secondPrice = parseFloat(element.price.substring(10));
                    let average = (firstPrice + secondPrice) / 2;

                    price += average;
                } else {
                     price += parseFloat(element.price.substring(1));
                }
            });

            return price.toFixed(2);
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
    display: flex;

    .areaData {
        flex-basis: 60%;

        .payArea {
            padding: 20px 0;
            display: flex;
            align-items: center;

            button {
                padding: 10px 70px;
                border-radius: 5px;
                margin: 0 10px;
                border: none;
                cursor: pointer;

                i {
                    font-size: 2rem;
                }
            }

            button:nth-child(1) {
                background-color: #000;

                i {
                    color: #fff;
                }
            }

            button:nth-child(2) {
                background-color: rgb(24, 24, 190);

                i {
                    color: #fff;
                }
            }

            button:nth-child(3) {
                background-color: rgb(230, 136, 49);

                i {
                    color: #fff;
                }
            }
        }
    }

    h4 {
        display: flex;
        justify-content: center;
        align-items: center;
        padding: 15px 0;
        text-align: center;
        color: rgb(133, 133, 133);

        &:after,
        &:before {
            content: "";
            margin: 0 10px;
            width: 40%;
            height: 1px;
            background-color: rgb(185, 185, 185);
            display: inline-block;
        }
    }

    #email {
        margin: 10px 20px;
        height: 40px;
        width: 50%;
        border-radius: 5px;
        border: 1px solid rgb(185, 185, 185);
        padding: 0 10px;

        &:focus-visible {
            outline: 2px solid rgb(69, 153, 221);
        }
    }

    .check {
        display: flex;
        margin: 0 20px 10px;
        cursor: default;

        #newsAndOffers {
            margin-right: 5px;
        }
    }

    form {
        margin: 20px 10px;

        .name {
            display: flex;

            #name,
            #surname {
                width: 40%;
                height: 40px;
                margin: 10px;
                border-radius: 5px;
                border: 1px solid rgb(185, 185, 185);
                padding: 0 10px;

                &:focus-visible {
                    outline: 2px solid rgb(69, 153, 221);
                }
            }
        }

        .elementForm {
            input {
                margin: 10px;
                height: 40px;
                width: calc(80% + 20px);
                border-radius: 5px;
                border: 1px solid rgb(185, 185, 185);
                padding: 0 10px;

                &:focus-visible {
                    outline: 2px solid rgb(69, 153, 221);
                }
            }
        }

        #submit {
            margin: 50px 0px 0px;
            height: 40px;
            width: 18%;
            border-radius: 25px;
            border: none;
            cursor: pointer;

            &:hover {
                background-color: rgb(214, 214, 214);
            }
        }
    }

    .areaSummary {
        flex-grow: 1;
        background-color: rgb(243, 243, 243);
        padding: 20px;
        height: 70vh;
        overflow-y: auto;

        h5 {
            font-size: 1rem;
            color: rgb(134, 134, 134);
            margin: 30px 0;
        }

        ul {
            margin: 30px 10px;

            li {
                padding: 5px 3px;
                display: flex;
                justify-content: space-between;

                span:nth-child(1) {
                    font-weight: 600;
                }
            }
        }

        div > h3{
            margin: 0 10px;
            text-align: end;
        }
    }
}
</style>
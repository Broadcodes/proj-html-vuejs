<template>
    <div class="container">
        <h2>Blog</h2>
        <div class="textImage">
            <div class="text">
                <h3>Keep up to date with the latest news:</h3>
                <h3>A little paw for the animals, a big step for humanity</h3>
            </div>
            <img src="../../public/images/8737.png"
                alt="Cats">
        </div>
        <div class="articles">
            <div class="card" v-for="article in articles" :key="article.id">
                <img :src="article.img"
                    :alt="article.autor">
                <div class="text">
                    <h2>{{article.title}}</h2>
                    <h4>{{article.article}}</h4>
                    <h5>{{article.autor}}</h5>
                    <h5>{{article.date}}</h5>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import { articles } from '@/data'

export default {
    name: 'BlogComponent',
    data(){
        return{
            articles
        }
    }
}
</script>

<style lang="scss" scoped>
.container {
    margin: 50px 10%;

    h2 {
        font-size: 3rem;
        padding: 20px 0;
    }

    .textImage {
        display: flex;
        background: rgb(181, 181, 181);
        background: linear-gradient(90deg, rgb(255, 255, 255) 20%, rgb(82, 82, 82) 80%);
        position: relative;

        .text {
            flex-basis: 80%;
            padding: 30px;

            h3:nth-child(1) {
                font-size: 4rem;
            }

            h3:nth-child(2) {
                font-size: 1.5rem;
                padding: 20px 0;
            }
        }

        img{
            flex-grow: 1;
            position: absolute;
            top: 20px;
            right: 20px;
            height: 150px;
            filter: invert(100%);
        }
    }

    .articles {
        margin: 50px 0px;
        padding-left: 150px;

        .card {
            display: flex;
            overflow-y: auto;
            margin: 30px 0;
            transition: transform .5s;

            img {
                max-width: 300px;
                object-fit: cover;
                padding: 20px;
            }

            .text {
                padding: 20px 40px;

                h2 {
                    padding: 0;
                    font-size: 2.7rem;
                }

                h4 {
                    padding: 20px 0;
                    font-weight: 300;
                }

                h5 {
                    color: rgb(146, 146, 146);
                }
            }

            &:hover{
                transform: scale(1.05);
                box-shadow: 10px 10px 10px rgb(163, 163, 163);
            }
        }

        .card:nth-child(odd) {
            background: rgb(232, 232, 232);
            background: linear-gradient(90deg, rgb(232, 232, 232) 20%, rgba(255, 255, 255, 0) 80%);
        }
    }
}
</style>
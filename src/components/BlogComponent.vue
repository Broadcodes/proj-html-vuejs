<template>
    <div class="container">
        <h2>Blog</h2>
        <div class="textVideo">
            <div class="text">
                <h3>Tieniti aggiornato sulle ultime news:</h3>
                <h3>Una piccola zampata per gli animali, un grande passo per l'umanità</h3>
            </div>
            <img src="https://1.bp.blogspot.com/-NAXf2ayt3ws/TuNxTmMew8I/AAAAAAAAlk4/HKPMLMIv8wI/s1600/the_definitive_collection_of_cat_47.gif"
                alt="Cats">
        </div>
        <div class="articles">
            <div class="card">
                <img src="https://1.bp.blogspot.com/-NAXf2ayt3ws/TuNxTmMew8I/AAAAAAAAlk4/HKPMLMIv8wI/s1600/the_definitive_collection_of_cat_47.gif"
                    alt="">
                <div class="text">
                    <h2>titolo</h2>
                    <h3>sottotitolo</h3>
                    <h4>articolo: Lorem ipsum dolor sit amet consectetur, adipisicing elit. Voluptas corrupti similique
                        perspiciatis. Quas repellendus laborum excepturi laudantium molestiae tempora fugiat eligendi
                        itaque rerum, ut eveniet magni, voluptatem illum quos deleniti?</h4>
                    <h5>autore</h5>
                    <h5>data</h5>
                </div>
            </div>
            <div class="card">
                <img src="https://1.bp.blogspot.com/-NAXf2ayt3ws/TuNxTmMew8I/AAAAAAAAlk4/HKPMLMIv8wI/s1600/the_definitive_collection_of_cat_47.gif"
                    alt="">
                <div class="text">
                    <h2>titolo</h2>
                    <h3>sottotitolo</h3>
                    <h4>articolo: Lorem ipsum dolor sit amet consectetur, adipisicing elit. Voluptas corrupti similique
                        perspiciatis. Quas repellendus laborum excepturi laudantium molestiae tempora fugiat eligendi
                        itaque rerum, ut eveniet magni, voluptatem illum quos deleniti?</h4>
                    <h5>autore</h5>
                    <h5>data</h5>
                </div>
            </div>
            <div class="card">
                <img src="https://1.bp.blogspot.com/-NAXf2ayt3ws/TuNxTmMew8I/AAAAAAAAlk4/HKPMLMIv8wI/s1600/the_definitive_collection_of_cat_47.gif"
                    alt="">
                <div class="text">
                    <h2>titolo</h2>
                    <h3>sottotitolo</h3>
                    <h4>articolo: Lorem ipsum dolor sit amet consectetur, adipisicing elit. Voluptas corrupti similique
                        perspiciatis. Quas repellendus laborum excepturi laudantium molestiae tempora fugiat eligendi
                        itaque rerum, ut eveniet magni, voluptatem illum quos deleniti?</h4>
                    <h5>autore</h5>
                    <h5>data</h5>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'BlogComponent'
}
</script>

<style lang="scss" scoped>
.container {
    margin: 50px 10%;

    h2 {
        font-size: 3rem;
        padding: 20px 0;
    }

    .textVideo {
        display: flex;
        background: rgb(181, 181, 181);
        background: linear-gradient(90deg, rgb(255, 255, 255) 20%, rgb(82, 82, 82) 80%);

        .text {
            padding: 30px;

            h3:nth-child(1) {
                font-size: 4rem;
            }

            h3:nth-child(2) {
                font-size: 1.5rem;
                padding: 20px 0;
            }
        }
    }

    .articles {
        margin: 50px 0px;
        padding-left: 150px;

        .card {
            display: flex;
            overflow-y: auto;
            margin: 30px 0;

            img {}

            .text {
                padding: 20px 40px;

                h2 {
                    padding: 0;
                    font-size: 2.7rem;
                }

                h3 {
                    color: rgb(96, 96, 96);
                }

                h4 {
                    padding: 20px 0;
                }

                h5 {
                    color: rgb(146, 146, 146);
                }
            }

        }

        .card:nth-child(odd) {
            background: rgb(232, 232, 232);
            background: linear-gradient(90deg, rgb(232, 232, 232) 20%, rgba(255, 255, 255, 0) 80%);
        }
    }
}
</style>
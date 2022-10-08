<template>
  <div class="container">
    <img src="@/assets/images/classic_thumbnail-600x450.jpg" alt="image contact">
    <div class="containerPage">
      <div class="text">
        <h2>
          Lorem, ipsum dolor sit amet consectetur adipisicing elit. Voluptate natus earum nam laboriosam rerum, commodi
          quisquam. Quae repellat dignissimos reprehenderit ipsam eligendi libero, repellendus a error saepe, aliquam,
          illum corporis!
        </h2>
      </div>
      <div class="infoAgency">
        <div class="textInfo">
          <h2>Vienici a trovare di persona</h2>
          <h3>Siamo aperti dal Lunedì al Venerdì</h3>
          <h3>Dalle 9.00 alle 13.00 e dalle 16.00 alle 20.00</h3>
          <h3>Sabato dalle 9.00 alle 13.00</h3>
        </div>
        <img src="@/assets/images/creative_thumbnail-600x450.jpg" alt="Image Contact">
      </div>
      <div class="infoMaps">
        <div class="map">
          MAPPA
        </div>
        <div class="textInfo">
          <h2>La nostra sede si trova in:</h2>
          <h3>Via Umberto I</h3>
          <h3>(presso ex palazzo comunale)</h3>
        </div>
      </div>
      <div class="form">
        <h2>Oppure</h2>
        <h2>contattaci al numero: 1.800.123.4567 o se preferisci</h2>
        <h2>scrivici compilando il seguente form:</h2>

        <form action="">
          <label for="name">Name</label>
          <input type="text" name="name" id="name">
          <label for="surname">Surname</label>
          <input type="text" name="surname" id="surname">
          <label for="surname">Email</label>
          <input type="email" name="email" id="email">
          <label for="message">Message</label>
          <textarea name="message" id="message" cols="100" rows="10"></textarea>
          <input type="submit" value="Submit">
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ContactComponent'
}
</script>

<style lang="scss" scoped>
.container {
  width: 100%;

  img {
    width: 100%;
    margin: 50px 0 0px;
    height: 400px;
    object-fit: cover;
    object-position: center;
  }

  .containerPage {
    margin: 50px 10%;

    .text {
      h2 {
        text-align: center;
        font-size: 1rem;
        line-height: 1.8rem;
      }
    }

    .infoAgency {
      display: flex;
      justify-content: center;
      align-items: center;
      margin: 50px 0;

      .textInfo {
        flex-basis: 50%;
        text-align: center;
      }

      img {
        flex-basis: 50%;
        border-top-right-radius: 60%;
        border-bottom-left-radius: 60%;
      }
    }

    .infoMaps {
      display: flex;
      justify-content: center;
      align-items: center;
      margin: 50px 0;

      .map {
        flex-basis: 50%;
      }

      .textInfo {
        flex-basis: 50%;
      }
    }

    .form{
      margin: 30px;
      text-align: center;

      h2:nth-child(1){
        font-size: 2rem;
      }

      h2{
        padding: 4px;
        font-size: 1.3rem;
      }

      form{
        margin: 40px 0;
        display: flex;
        flex-direction: column;
        align-items: center;
        text-align: left;

        label,
        input,
        textarea{
          width: 750px;
        }

        input,
        textarea{
          margin: 10px 0;
          padding: 10px;
        }

        input:nth-child(9){
          width: 180px;
          border-radius: 25px;
          color: #fff;
          background-color: #3d6f42;
          border: none;
          cursor: pointer;

          &:hover {
            background-color: #529258;
          }
        }
      }
    }
  }


}
</style>
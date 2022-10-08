<template>
  <div class="container">
    <img src="@/assets/images/classic_thumbnail-600x450.jpg" alt="image contact">
    <div class="containerPage">
      <div class="text">
        <h2>
          Contact us for advice on symptoms, causes and remedies of the dog's "re-entry stress" to be prepared for the
          return from vacation, or are you about to leave for a holiday in the mountains with your cat and do not know
          how to organize yourself? We do it for you!
        </h2>
      </div>
      <div class="infoAgency">
        <div class="textInfo">
          <h2>Come and see us in person</h2>
          <h3>We are open from Monday to Friday</h3>
          <h3>From 9.00AM to 1.00PM and from 4.00AM to 8.00PM</h3>
          <h3>Saturday from 9.00AM to 1.00PM</h3>
        </div>
        <img src="@/assets/images/creative_thumbnail-600x450.jpg" alt="Image Contact">
      </div>
      <div class="infoMaps">
        <div class="map">
          <iframe
            src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d24789.235328022598!2d-77.00431065396835!3d39.04599819105301!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x89b7c59f75842a0b%3A0x7fdcc2c8cd0e169b!2sWhite%20Oak%2C%20Maryland%2C%20Stati%20Uniti!5e0!3m2!1sit!2sit!4v1665253998759!5m2!1sit!2sit"
            width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy"
            referrerpolicy="no-referrer-when-downgrade"></iframe>
        </div>
        <div class="textInfo">
          <h2>Our headquarters are located in:</h2>
          <h3>1234 Avada Avenue Avadaville</h3>
          <h3>(in the former town hall)</h3>
        </div>
      </div>
      <div class="form">
        <h2>Or</h2>
        <h2>contact us at: 1.800.123.4567 or if you prefer</h2>
        <h2>write to us by filling out the following form:</h2>
        <h2>or by sending us an email at info@your-company.com</h2>

        <form method="post">
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

        h2,
        h3 {
          padding: 5px 0;
        }
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
      margin: 100px 0;

      .map {
        flex-basis: 50%;
      }

      .textInfo {
        flex-basis: 50%;
        margin-left: 50px;

        h2,
        h3 {
          padding: 5px 0;
        }
      }
    }

    .form {
      margin: 30px;
      text-align: center;

      h2:nth-child(1) {
        font-size: 2rem;
      }

      h2 {
        padding: 4px;
        font-size: 1.3rem;
      }

      form {
        margin: 40px 0;
        display: flex;
        flex-direction: column;
        align-items: center;
        text-align: left;

        label,
        input,
        textarea {
          width: 750px;
        }

        input,
        textarea {
          margin: 10px 0;
          padding: 10px;
        }

        input:nth-child(9) {
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
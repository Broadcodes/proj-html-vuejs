<template>
  <div class="container">
    
    <div class="jumbo">
      <img src="@/assets/img/dogs-cat-together-with-pink-background_539007-7.jpg" alt="Avada Avenue Avadaville">
      <h2>Avada Avenue Avadaville</h2>
      <h2>Noi... per il benessere degli animali</h2>
    </div>
    <h2>Chi Siamo</h2>
    <div class="textImage">
      <p>
        Lorem ipsum dolor sit, amet consectetur adipisicing elit. Hic sint vel, at eligendi itaque illum explicabo
        a amet, id ea vitae minima veritatis officia molestias corporis. Quas aspernatur eum ea.
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Saepe eveniet consequatur pariatur illo tenetur
        exercitationem eligendi, suscipit temporibus aspernatur impedit, ipsa, sequi ullam tempore id sit obcaecati
        in quisquam deleniti!
      </p>
      <img src="@/assets/images/vet_thumbnail-600x450.jpg" alt="Avada Avenue Avadaville">
    </div>
    <h2>La nostra azienda</h2>
    <div class="textImage">
      <img src="@/assets/images/agency_thumbnail-600x450.jpg" alt="Avada Avenue Avadaville">
      <p>
        Lorem ipsum dolor sit, amet consectetur adipisicing elit. Hic sint vel, at eligendi itaque illum explicabo
        a amet, id ea vitae minima veritatis officia molestias corporis. Quas aspernatur eum ea.
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Saepe eveniet consequatur pariatur illo tenetur
        exercitationem eligendi, suscipit temporibus aspernatur impedit, ipsa, sequi ullam tempore id sit obcaecati
        in quisquam deleniti!
      </p>
    </div>

    <input type="button" value="Contact us" @click="setPage">

  </div>
</template>

<script>
export default {
  name: 'AboutComponent',
  methods: {
    setPage() {
      this.$emit('page', 'Contact');
    }
  }
}
</script>

<style lang="scss" scoped>
.container {
  text-align: center;

  h2{
    font-size: 3rem;
    margin: 30px;
  }

  .jumbo{
    width: 100%;
    height: 550px;
    position: relative;
    overflow: hidden;

    h2{
      font-size: 3.5rem;
      color: #fff;
      position: absolute;
      transition: all .5s;
    }

    h2:nth-child(2){
      top: 35%;
      right: 10%;
      transform: translateY(-50%);
      animation: moveDxToSx ease-in-out 1 1.5s;
    }

    @keyframes moveDxToSx {
      from {right: -50%; color: rgba(255, 255, 255, 0);}
      to{right: 10%; color: #fff;}
    }

    h2:nth-child(3){
      top: 55%;
      left: 10%;
      transform: translateY(-50%);
      animation: moveSxToDx ease-in-out 1 1.5s;
    }

    @keyframes moveSxToDx {
      from {left: -50%; color: rgba(255, 255, 255, 0);}
      to{left: 10%; color: #fff;}
    }

    img{
      width: 100%;
      height: 100%;
      object-fit: cover;
      filter: brightness(70%);
    }
  }

  .textImage {
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 50px 10%;

    p{
      padding: 20px;
      margin: 0 100px;
      transition: all 1s;
    }

    p:nth-child(1){
      &:hover{
        transform: scale(1.05);
        box-shadow: -20px 20px 20px rgb(143, 143, 143);
      }
    }

    p:nth-child(2) {
      &:hover{
        transform: scale(1.05);
        box-shadow: 20px 20px 20px rgb(143, 143, 143);
      }
    }
  }

  input{
    padding: 20px 50px;
    border-radius: 50px;
    font-size: 1rem;
    border: none;
    color: #fff;
    background-color: #3d6f42;
    margin-bottom: 40px;

    &:hover{
      background-color: #528f58;
      cursor: pointer;
    }
  }
}
</style>
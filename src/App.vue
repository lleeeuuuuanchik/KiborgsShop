<style>
  @import url("./assets/styles/reset.css");
  @import url("./assets/styles/main.css");
  @import url("./assets/styles/header.css");
  @import url("./assets/styles/section-slider.css");
  @import url("./assets/styles/first-product.css");
</style>

<template>
  <header class="header">
    <div class="header__head">
      <div class="container">
        <div class="head">
          <img src="./assets/img/logo/LIMX.svg" class="head__logo" alt="logo">   
          <nav class="head__nav">
            <a href="" class="nav__a">products</a>
            <a href="" class="nav__a">about us</a>
          </nav>
          <nav class="head__cart-login">
            <img src="./assets/img/icons/cart.svg" alt="">
            <img src="./assets/img/icons/login.svg" alt="">
          </nav>  
        </div>
      </div>
    </div>
    <div class="container">    
      <div class="header-slogan">
        <h1 class="slogan-main">make yourself<br>smarter</h1>
        <p class="slogan-second">technological life closer than you think</p>
        <button class="btn slogan-btn">get it</button>
      </div>    
    </div>
  </header>


  <section class="slider">
    <div class="container">
      <h2 class = "slider-h">The most popular products</h2>
      <div class="slider-container">
         <carousel :items-to-show="1" :autoplay="5000" :transition="1500" :wrap-around="true" :touchDrag="false" :mouseDrag="false">
          <slide v-for="(item, index) in sliderArray" :key="index">
            <img :src="require(`./assets/img/forSlider/${item.img}` )" class="slider-img" alt="">
          </slide>
          <template #addons>
            <navigation />
          </template>
        </carousel>
      </div>
    </div>
    
  </section>


  <section class="first-product">
    <div class="container">
      <div class="first-product__about">
        <div class="about-information">
          <div class="about-first">
            <h3 calss="about-slogan">LIMX`s first product</h3>
            <p class="about-inf">Limx body d3000 - our first product, it got “the best KIBER product in 2040y” and it is our pride</p>
            <p class="about-inf">It was our genius thing, which turned the kiborgs world</p>
          </div>

          <div class="about-second">
            <p class="about-inf">If you want to see more of our products then click the button below</p>
            <button class="btn about-btn">see more</button>
          </div>
        </div>       
        <img src="./assets/img/about.jpg" class="about-img" alt="">     
      </div>
      
    </div>
  </section>
</template>






<script>
  import 'vue3-carousel/dist/carousel.css';
  import { Carousel, Slide, Navigation } from 'vue3-carousel';
  export default {
    name: 'App',
    data() {
      return {
        sliderArray: [
          {id: 1, img: "head.jpg"},
          {id: 2, img: "hand.jpg"},
          {id: 3, img: "body.jpg"} ]
      }
    },
    components: {
      Carousel,
      Slide,
      Navigation,
    },
  };
</script>



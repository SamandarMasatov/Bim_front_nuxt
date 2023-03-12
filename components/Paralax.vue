<template>
  <div id="signup">
    <v-parallax height="600" src="/img/paralax-img.jpg" class="paralax" id="SignUp">
      <div class="blur text-center pt-16">
        <v-container>
          <h5 data-aos="fade-up">Hoziroq ro'yxatdan o'ting</h5>
        <h2 class="my-5">
          Hoziroq Kursimizga qo'shiling va 20% chegirmaga ega bo'ling
        </h2>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
          eiusmod <br />
          tempor incididunt ut labore et dolore magna aliqua
        </p>
        </v-container>
      </div>
    </v-parallax>
  </div>
</template>



<style scoped>
.paralax {
  position: relative;
  z-index: 100;
}
h5 {
  color: #ce373a;
  font-family: 'Playfair Display', sans-serif !important;
  font-size: 20px !important;
  font-weight: 500 !important;
  font-style: italic !important;
  line-height: 1em !important;
}
.blur {
  width: 100% !important;
  height: 100% !important;
  background-color: #1b1f2d;
  opacity: 0.91;
  position: absolute;
  top: 0;
  left: 0;
}
.v-parallax__content {
  padding: 0 !important;
}
p{
  color:#cdd1de;
}
</style>

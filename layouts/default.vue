<template>
  <v-app dark>
    <Header />
    <v-main>
        <Nuxt />
    </v-main>
    <Footer />
    <a href="#">
      <v-btn
      class="ma-2 button-scrol"
      fab
      color="#ce373a"
      
    >
      <v-icon class="scrol-icon">mdi-chevron-double-up</v-icon>
    </v-btn>
    </a>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',

  mounted(){
    let button = document.querySelector(".button-scrol")

    window.addEventListener("scroll", () => {
      button.classList.toggle('button-active', scrollY > 100)
    })
  }
}
</script>

<style >
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@1,500&display=swap');
@import url('https://fonts.googleapis.com/css2?family=DM+Sans:ital,wght@0,400;1,700&display=swap');
*{
  scroll-behavior: smooth;
}
.button-scrol{
  position: fixed;
  bottom: 30px;
  right: 30px;
  z-index: 20000;
  transform: scale(0);
  transition: 0.5s;
}
.button-active{
  transform: scale(1);
  
}
.scrol-icon{
  color: #fff !important;
}
button{
  font-family: 'DM Sans' !important;
}
</style>

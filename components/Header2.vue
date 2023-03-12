<template>
  <div class="header">
    <v-container class="d-flex align-center justify-space-between">
      <div class="logo ">
        <Nuxt-link to="/" class="d-flex align-center"><v-img class="logo-img" src="/images/logotip.png"></v-img>
        <div class="title">Baxshichilik</div></Nuxt-link>
      </div>
      <ul class="d-none d-lg-block ul">
        <li>
          <Nuxt-link to="/" class="link link-active">Home</Nuxt-link>
        </li>
        <li>
          <a href="#about" class="link">Biz haqimizda</a>
        </li>
        <li>
          <a href="#news" class="link">Yangiliklar</a>
        </li>
        <li>
          <a href="#kurs" class="link">Kurslar</a>
        </li>
        <li>
          <a href="#SignUp" class="link">Qabulga yozilish</a>
        </li>
      </ul>
      <div class="auth">
        <v-btn
          elevation="0"
          class="btn sign-up me-5 d-none white--text d-md-inline-block"
          >Ro'yxatdan o'tish</v-btn
        >
        <v-btn elevation="0" class="btn log-in d-none d-md-inline-block"
          >Kirish</v-btn
        >
        <v-btn elevation="0" @click="printMenu()" class="ms-5 icon d-lg-none">
          <v-icon v-if="menu">mdi-menu</v-icon>
          <v-icon v-else>mdi-close-thick</v-icon>
        </v-btn>
      </div>
    </v-container>
    <div class="print-menu d-lg-none">
      <ul>
        <li>
          <a href="#home" class="link-active">Home</a>
        </li>
        <li>
          <a href="#about">Biz haqimizda</a>
        </li>
        <li>
          <a href="#">Kurslar</a>
        </li>
        <li>
          <a href="#">Yangiliklar</a>
        </li>
        <li>
          <a href="#">Qabulga yozilish</a>
        </li>
        <li class="d-md-none">
          <v-btn elevation="0" dark class="md-btn btn-utish"
            >Ro'yxatdan o'tish</v-btn
          >
        </li>
        <li class="d-md-none">
          <v-btn elevation="0" class="md-btn btn-kirish">Kirish</v-btn>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      active: false,
      menu: true,
    }
  },
  methods: {
    printMenu() {
      if (this.menu) {
        document.querySelector('.print-menu').style.right = 0
        document.querySelector('.header').style.background = 'black'
        this.menu = false
      } else {
        document.querySelector('.print-menu').style.right = -100 + '%'
        this.menu = true
      }
    },
  },
}
</script>

<style scoped>
a{
  text-decoration: none;
  color: #fff;
}
.print-menu {
  position: fixed;
  top: 96px;
  right: -100%;
  transition: 0.5s ease all;
  width: 50%;
  height: 100%;
  padding: 70px 50px;
  background: black;
  display: flex;
}
.print-menu ul {
  width: 100%;
  height: 60%;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
}
.print-menu ul li {
  list-style-type: none;
  padding: 10px 0;
}
.print-menu ul li a {
  font-size: 20px;
  text-decoration: none;
  color: white;
  font-weight: bold;
  transition: 0.5s ease all;
  text-transform: uppercase;
}
.print-menu ul li a:hover {
  color: #ce373a;
}
.header {
  background: black;
  color: white;
  position: fixed;
  width: 100%;
  height: auto;
  border-bottom: 2px solid #565656;
  z-index: 4000;
  transition: 0.5s ease all;
  top: 0;
  left: 0;
}
.header-active {
  background: white;
}
.logo-img {
  width: 70px;
  height: 70px;
  border-radius: 50%;
  background: white !important;
}
.logo .title {
  font-size: 20px;
  margin-left: 10px;
  text-transform: uppercase;
}
.link {
  font-size: 12px;
  text-transform: uppercase;
  text-decoration: none;
  transition: 0.5s ease all;
  color: white;
  font-weight: bold;
}
.link:hover {
  color: #ce373a;
}
.link-active {
  color: #ce373a !important;
}
.ul li {
  list-style-type: none;
  display: inline-block;
}
.ul li:not(:first-child) {
  padding-left: 36px;
}
.auth .btn {
  background: #ce373a;
  padding: 10px 18px;
  font-size: 14px;
  font-weight: bold;
  cursor: pointer;
  border: none !important;
  border-radius: 0px !important;
}
.log-in {
  background: white !important;
  color: #ce373a;
}
.icon {
  border-radius: 0px;
  background: #ce373a !important;
  color: white !important;
  font-size: 25px;
}
.md-btn {
  border: none !important;
  border-radius: 0px !important;
  font-weight: bold !important;
}
.btn-utish {
  background-color: #ce373a !important;
  /* color: white !important; */
}
.btn-kirish {
  background: white !important;
  color: #ce373a !important;
}
@media (max-width: 700px) {
  .print-menu {
    width: 100%;
  }
}
</style>

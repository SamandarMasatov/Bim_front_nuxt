<template>
  <div class="footer">
    <div class="container">
      <v-row justify="center" align="center">
        <v-col align-self="center" cols="12" md="6" lg="3">
          <div class="logo">
        <Nuxt-link to="/" class="d-flex align-center logo-link"><img height="120px" width="100px" class="logo-img" src="/images/logotip.png"/>
        <div class="title">Baxshichilik</div></Nuxt-link>
      </div>  
          <!-- <v-img max-width="200" class="mt-5" src="/image\logo.png"></v-img> -->
          <p class="my-5">
            Lorem ipsum dolor sit amet, consectet adipiscing elit, sed do
            eiusmod
          </p>
          <div>
            <v-icon class="my-5" color="#ff6900">mdi-map-marker</v-icon
            ><span>Бахшичилик мактаби, 68M8+74Q, Termez</span>
            <v-spacer></v-spacer>
            <v-icon color="#ff6900">mdi-email</v-icon
            ><span>Jl. Raya Ubud No 11, Ubud</span>
            <v-spacer></v-spacer>
            <v-icon color="#ff6900">mdi-phone</v-icon
            ><span>+998 - - - - - - - - -</span>
          </div>
        </v-col>
        <v-spacer> </v-spacer>
        <v-col class="px-5 px-md-none" cols="12" md="6" lg="2">
          <h4>Tezkor havolalar</h4>
          <hr class="hr" />
          <ul>
            <li>Biz haqimizda</li>
            <li>Sinf</li>
            <li>O'qituvchilar</li>
            <li>Blog</li>
            <li>Contact</li>
          </ul>
        </v-col>
        <v-col class="px-5 px-md-none" cols="12" md="6" lg="3">
          <h4>Foydali havolalar</h4>
          <hr class="hr" />
          <ul>
            <li>Maxfiylik siyosati</li>
            <li>Foydalanish shartlari</li>
            <li>Rad etish</li>
            <li>Qo'llab-quvvatlash</li>
            <li>Ish vaqti</li>
          </ul>
        </v-col>
        <v-col class="px-5 px-md-none" cols="12" md="6" lg="4">
          <h4>Ish vaqti</h4>
          <hr class="hr" />
          <ul>
            <li>9:00 dan 17:00 gacha, dushanbadan shanbagacha</li>
            <li class="text">
              Lorem ipsum dolor sit amet, consectectur adipiscing elit, sed do
              eiusmod tempor
            </li>
            <li><v-btn class="button2 my-5">REGISTER NOW</v-btn></li>
          </ul>
        </v-col>
      </v-row>
      <hr class="my-5 w-100" />
      <v-row justify="center">
        <v-col class="footer_url" cols="12" md="6">
          Art & Drawing School Template Kit by Jegtheme</v-col
        >
        <v-col class="footer_url" cols="12" md="6">
          <v-spacer></v-spacer> Copyright © 2022. All rights reserved.</v-col
        >
      </v-row>
    </div>
  </div>
</template>
<script>
export default {
  data: () => ({}),
}
</script>
<style scoped>
.logo-link{
  text-decoration: none;
  color: #fff;
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
.footer {
  background-color: #181d23;
  color: #fff;
  margin: 0;
}
p {
  opacity: 0.5;
}
hr {
  width: 100% !important;
  opacity: 0.5;
}
.footer_url {
  opacity: 0.5;
}
.hr {
  color: #ce373a !important;
  width: 100px !important;
  height: 2.5px;
  background-color: #ce373a;
  border: none;
  /* opacity: 0.5; */
}
ul{
  padding-left: 0;
  padding-right: 0;
  padding-top: 20px;
}
ul li {
  list-style: none !important;
  line-height: 40px;
  transition: all 0.5s ease;
  cursor: pointer;
}
ul li:hover {
  color: #cf2e2e;
}
.text{
  font-size: 16px;
  line-height: 20px;
}
.button2 {
  width: 150px;
  padding: 25px 40px !important;
  text-transform: uppercase;
  border-top-left-radius: 20px;
  border-top-right-radius: 0;
  border-bottom-right-radius: 20px;
  border-bottom-left-radius: 0;
  background-color: #ce373a !important;
  color: #fff;
  transition-duration: 0.3s;
  transition-property: transform;
  transition-timing-function: ease-out;
  position: relative;
  z-index: 0;
}
.button2:hover {
  background-color: white !important;
  color: black;
}
h4 {
  font-size: 18px;
  font-family: 'DM Sans' !important;
}
</style>

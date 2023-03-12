<template>
  <div class="sign_up_background">
    <div class="blur"></div>
    <v-container class="sign-up">
      <v-container fluid class="fluid-sign pa-10">
        <v-row justify="space-between" class="form">
          <v-col cols="12" class="mb-10"
            ><h2 class="text-center">Online ro'yxatdan o'tish</h2></v-col
          >
          <v-col cols="12" lg="6">
            <v-form ref="form">
              <v-row>
                <v-col cols="12">
                  <label for="name">Ism Familyani kiriting</label>
                  <v-text-field
                    id="name"
                    v-model="name"
                    :counter="10"
                    :rules="nameRules"
                    label="Ism Familya"
                    required
                    outlined
                    class="mt-3"
                  ></v-text-field>
                </v-col>
                <v-col cols="12" lg="6">
                  <label for="Email">Emailni kiriting</label>
                  <v-text-field
                    id="Email"
                    v-model="email"
                    :rules="emailRules"
                    label="E-mail"
                    required
                    outlined
                    class="mt-3"
                  ></v-text-field>
                </v-col>
                <v-col cols="12" lg="6">
                  <label for="Telephone">Telefon raqamingizni kiriting</label>
                  <v-text-field
                    type="number"
                    id="Telephone"
                    v-model="telephone"
                    :counter="13"
                    :rules="phoneRules"
                    label="Telefon raqam"
                    required
                    outlined
                    class="mt-3"
                  ></v-text-field>
                </v-col>
                <v-col cols="12">
                  <label for="animal">O'zingiz yoqtirgan kursni tanlang</label>
                  <v-select
                    id="animal"
                    :items="animals"
                    :rules="animal"
                    color="pink"
                    label="Kurslarni tanlang"
                    required
                    outlined
                    class="mt-3"
                  ></v-select>
                </v-col>
                <v-col cols="12">
                  <v-textarea
                    :rules="messageRules"
                    outlined
                    name="input-7-4"
                    label="Xabar yuboring"
                    class="mt-3"
                  ></v-textarea>
                </v-col>
              </v-row>
              <v-btn depressed class="button mt-5"> Ro'yhatdan O'tish </v-btn>
            </v-form>
          </v-col>
          <v-col cols="12" lg="5" class="connect pa-0 mt-5 mt-lg-0">
            <div class="connect_blur pa-3 pa-sm-10">
              <h3 class="white--text">
                Agar sizda biron bir savol bo'lsa, biz bilan bog'lanishdan
                tortinmang
              </h3>
              <p class="my-5">
                Lorem ipsum dolor sit amet, consectet adipiscing elit, sed do
                eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut
                enim ad minim
              </p>
              <ul class="pa-0 my-5 text">
                <li class="d-flex mb-3 p-0">
                  <p><v-icon class="icon d-block">mdi-check-circle</v-icon></p>
                  <p class="">Consectetuer adipiscing elit. Aenean commodo</p>
                </li>
                <li class="d-flex">
                  <p><v-icon class="icon d-block">mdi-check-circle</v-icon></p>
                  <p class="">Excepteur sint occaecat cupidatat non proident</p>
                </li>
              </ul>
              <v-btn class="button2">view class</v-btn>
              <ul class="address pa-0 my-5">
                <li class="mb-3 d-flex">
                  <v-icon class="icon me-3 d-block"
                    >mdi-map-marker-radius</v-icon
                  >Бахшичилик мактаби, 68M8+74Q, Termez
                </li>
                <li class="d-flex">
                  <v-icon class="icon me-3">mdi-phone-in-talk</v-icon>+998 --
                  --- -- --
                </li>
              </ul>
            </div>
          </v-col>
        </v-row>
      </v-container>
      <div class="text-center title">
        <h5>Bizning jarayonimiz</h5>
        <h2 class="my-5">Biz qanday ishlaymiz</h2>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
          eiusmod
          <br />
          tempor incididunt ut labore et dolore magna aliqua
        </p>
      </div>
      <v-row class="mt-16" justify="center">
        <v-col cols="12" sm="6" md="4" class="">
          <v-card class="mx-auto card text-center pa-6">
            <div class="card-icon">
              <i class="fa-regular fa-pen-to-square"></i>
            </div>

            <h3 class="card-title mt-10">Kursingizni tanlang</h3>

            <v-card-subtitle class="card-subtitle"
              >Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
              eiusmod tempor incididunt ut labore et dolore</v-card-subtitle
            >
          </v-card>
        </v-col>
        <v-col cols="12" sm="6" md="4">
          <v-card class="mx-auto card text-center pa-6">
            <div class="card-icon">
              <i class="fa-regular fa-pen-to-square"></i>
            </div>

            <h3 class="card-title mt-10">Bizning kursimizga qo'shiling</h3>

            <v-card-subtitle class="card-subtitle"
              >Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
              eiusmod tempor incididunt ut labore et dolore</v-card-subtitle
            >
          </v-card>
        </v-col>
        <v-col cols="12" sm="6" md="4">
          <v-card class="mx-auto card text-center pa-6">
            <div class="card-icon">
              <i class="fa-regular fa-pen-to-square"></i>
            </div>

            <h3 class="card-title mt-10">Ijodingizdan zavqlaning</h3>

            <v-card-subtitle class="card-subtitle"
              >Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
              eiusmod tempor incididunt ut labore et dolore</v-card-subtitle
            >
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  data: () => ({
    name: null,
    telephone: null,

    nameRules: [(v) => !!v || "To'ldirilishi shart"],
    email: '',
    emailRules: [
      (v) => !!v || 'Email kiritilishi shart',
      (v) => /.+@.+\..+/.test(v) || 'E-mail must be valid',
    ],
    animal: [(v) => !!v || 'Tanlash shart'],
    phoneRules: [
      (v) => !!v || 'Telefon raqam kiritilishi shart',
      (val) => (val || '').length <= 12 || "Noto'g'ri raqam",
    ],
    messageRules: [(val) => (val || '').length > 0 || "To'ldirilishi shart"],
    animals: ['Ananaviy sozandalik', 'Ananaviy honandalik', 'Baxshichilik'],
  }),
}
</script>

<style scoped>
.border {
  border: 1px solid;
}
li {
  list-style: none;
}
.sign_up_background {
  background: url('https://templatekit.jegtheme.com/articio/wp-content/uploads/sites/230/2022/01/pattern.jpeg');
  background-size: cover;
  position: relative;
  direction: flex;
  justify-content: center;
  height: 1500px;
}
.sign-up {
  position: absolute;
  z-index: 1000;
  top: -250px;
  right: 0;
  left: 0;
}
.fluid-sign {
  background-color: #fff;
  box-shadow: 0px 5px 30px 0px rgb(0 0 0 / 10%);
  border-top-left-radius: 30px !important;
  border-bottom-right-radius: 30px !important;
}
.title {
  margin-top: 100px;
}
.button {
  padding: 30px 40px !important;
  text-transform: uppercase;
  border-top-left-radius: 20px;
  border-top-right-radius: 0;
  border-bottom-right-radius: 20px;
  border-bottom-left-radius: 0;
  background-color: #ce373a !important;
  color: #fff;
  transition: 0.4s;
}
.text li {
  display: flex;
  align-items: center;
}
.button:hover {
  background-color: #2d3448 !important;
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
  position: relative;
  transition: 0.5s !important;
}
.button2:hover {
  background-color: white !important;
  color: black;
  top: -20px;
}
.connect {
  background: url('/img/baxshi-bola.jpg') no-repeat center;
  background-size: cover;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  border-top-left-radius: 20px !important;
  border-bottom-right-radius: 20px !important;
  overflow: hidden;
}
.connect_blur {
  width: 100% !important;
  height: 100% !important;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  background-color: #1b1f2d;
  opacity: 0.91;
}
.connect_blur p {
  color: #cdd1de;
}
.connect_blur li {
  color: #cdd1de;
}
.icon {
  color: #ce373a;
  overflow: hidden;
}
.blur {
  width: 100% !important;
  height: 100% !important;
  display: flex;
  flex-direction: column;
  justify-content: center;
  background-color: #ffffffd2;
}
h5 {
  color: #ce373a;
  font-size: 20px;
  font-family: 'Playfair Display', sans-serif !important;
  font-size: 20px !important;
  font-weight: 500 !important;
  font-style: italic !important;
  line-height: 1em !important;
}
h3 {
  font-family: 'DM Sans' !important;
}
p {
  color: #62697c;
  font-size: 16px;
}
label {
  color: #62697c;
  font-size: 16px;
  font-family: 'DM Sans' !important;
}
h2 {
  color: #2d3448;
  font-family: 'DM Sans' !important;
}
.card {
  background-color: rgb(234, 223, 223, 0.1) !important;
}
.card-title {
  color: #2d3448;
}
.card-subtitle {
  color: #62697c;
}
.card-icon {
  width: 120px;
  height: 120px;
  margin: 0 auto;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #fff;
  box-shadow: 0px 5px 30px 0px rgb(0 0 0 / 10%);
  border-top-left-radius: 20px !important;
  border-bottom-right-radius: 20px !important;
  transition: 0.6s;
}
.card:hover .card-icon {
  background-color: #ce373a;
}
.card i {
  font-size: 50px;
  color: #ce373a;
  transition: 0.6s;
}
.card:hover i {
  color: #fff !important;
}

@media (max-width: 1264px) {
  .sign_up_background {
    height: 2200px;
  }
}
@media (max-width: 961px) {
  .sign_up_background {
    height: 2550px;
  }
}
@media (max-width: 640px) {
  .sign_up_background {
    height: 2810px;
  }
}
@media (max-width: 500px) {
  .sign_up_background {
    height: 3300px;
  }
}
</style>

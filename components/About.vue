<template>
  <div id="about">
    <v-container>
      <v-row
        style="position: relative; box-sizing: border-box; padding: 40px 0"
      >
        <v-col cols="12" md="4">
          <div class="item d-flex">
            <img src="/images/pacel.png" style="object-fit: cover" />
            <div class="text">
              <div class="title">Mahoratli Ustozlar</div>
              <p>
                Lorem ipsum dolor sit amet, consect adipiscing elit sed do
                eiusmod
              </p>
            </div>
          </div>
        </v-col>
        <v-col cols="12" md="4">
          <div class="item d-flex">
            <img src="/images/dollar.png" style="object-fit: cover" />
            <div class="text">
              <div class="title">Mutlaqo bepul</div>
              <p>
                Lorem ipsum dolor sit amet, consect adipiscing elit sed do
                eiusmod
              </p>
            </div>
          </div>
        </v-col>
        <v-col
          cols="12"
          md="4"
          style="position: relative; box-sizing: border-box"
        >
          <div class="practic absolute end-0 bottom-0 px-15 py-10 white--text">
            <div class="title w-100 d-flex align-center justify-space-between">
              <span class="year"
                >{{ new Date().getFullYear() - 2010 }}
                <span class="plus">+</span></span
              >
              <span>Yillik mahorat <br />va tajriba</span>
            </div>
            <div class="p">Ijodkor shaxs uchun ijodiy maydon</div>
            <div class="lorem">
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut elit
              tellus, luctus nec ullamcorper mattis pulvinar
            </div>
          </div>
        </v-col>
      </v-row>
      <v-row v-for="item of about" :key="item._id">
        <v-col
          cols="12"
          md="6"
          class="d-flex align-center justify-center"
          style="position: relative"
        >
          <div class="about-img mt-5">
            <img
              :src="`http://localhost:3030/uploads/about/${item.file[0]}`"
              class="img-1"
              alt=""
            />
            <div class="img-2">
              <img
                :src="`http://localhost:3030/uploads/about/${item.file[1]}`"
                alt=""
              />
            </div>
          </div>
        </v-col>
        <v-col cols="12" md="6">
          <div class="about-baxshi">
            <div class="title">Baxshichilik san'ati haqida</div>
            <div class="p">
              San'atni tubdan o'rganing va ishtiyoqingizga intiling
            </div>
            <p class="lorem">
              {{ item.description }}
            </p>
            <div class="event">
              <div class="w-100 d-flex align-center justify-space-between">
                <div
                  class="number text-center my-5"
                  style="width: 35%; border-right: 3px solid #ccc"
                >
                  {{ item.student }} <span>+</span>
                  <br />
                  <p>Barcha Talabalar</p>
                </div>
                <div class="ps-5 value" style="width: 65%">
                  {{ item.studentTitle }}
                </div>
              </div>
              <div class="w-100 d-flex align-center justify-space-between">
                <div
                  class="number text-center my-5"
                  style="width: 35%; border-right: 3px solid #ccc"
                >
                  {{ item.prize }} <span>+</span>
                  <br />
                  <p>Sovrin va Yutuqlar</p>
                </div>
                <div class="ps-5 value" style="width: 65%">
                  {{ item.prizeTitle }}
                </div>
              </div>
            </div>
            <div class="person w-100 d-flex align-center text-center">
              <img src="/images/home.png" alt="" />
              <div class="name">
                <b>Russell Mack</b> <br />
                Baxshi
              </div>
              <v-btn class="more" elevation="0" to="/About"> Batafsil </v-btn>
            </div>
          </div>
        </v-col>
      </v-row>
    </v-container>
    
  </div>
</template>

<script>
export default {
  name: 'About',
  data() {
    return {
      about: [],
    }
  },

  mounted() {
    this.$axios.get('/about/getAll').then((res) => {
      this.about = res.data
    })
    console.log(this.about)
  },
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display&display=swap');

.person .more {
  border-radius: 10px 0 10px 0;
  font-size: 12px;
  padding: 18px 32px !important;
  display: inline-block;
  height: 48px;
  background: #ce373a;
  color: white;
  font-weight: bold;
}
.item .result {
  width: 100%;
  background: white;
  border-radius: 5px 0 5px 0;
  overflow: hidden;
}
.item .result .result-value {
  width: 89%;
  background: #ce373a;
  padding: 6px;
  border-radius: 5px 0 5px 0;
}
.about-footer {
  width: 100%;
  position: relative;
}
.about-footer .about-footer-left {
  padding: 90px 60px 90px 0;
  color: white;
}
.about-footer .about-footer-left .footer-title {
  font-size: 36px;
  font-weight: bold;
  line-height: 45px;
  font-family: 'DM Sans' !important;
}
.about-footer .about-footer-left .footer-p {
  font-size: 16px;
  font-weight: bold;
  color: #cdd1de;
  margin: 20px 0;
}
.about-footer img {
  width: 100%;
  height: 100%;
  position: absolute;
  left: 0;
  top: 0;
  object-fit: cover;
  z-index: 0;
}
.about-footer .bg {
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  z-index: 1;
  background: rgba(0, 0, 0, 0.402);
}
.about-footer .bg-2 {
  position: absolute;
  left: 0;
  top: 0;
  width: 50%;
  height: 100%;
  z-index: 1;
  background: rgba(0, 0, 0, 0.676);
}
.person .more {
  border-radius: 10px 0 10px 0;
  font-size: 12px;
  padding: 18px 32px !important;
  display: inline-block;
  height: 48px;
  background: #ce373a;
  color: white;
  font-weight: bold;
}
.person img {
  width: 63px;
  height: 63px;
  object-fit: cover;
  border-radius: 50%;
}
.person .name {
  font-size: 16px;
  color: #62697c;
  padding: 0 40px 0 20px;
}
.person .name b {
  font-size: 20px;
  color: #2d3448;
}
.event .number {
  font-size: 40px;
  font-weight: bold;
  color: #ce373a;
}
.event .number span {
  font-size: 24px;
  color: #2d3448;
  position: relative;
  top: -7px;
}
.event .number p {
  color: #62697c;
  font-size: 16px;
}
.event .value {
  color: #62697c;
  font-size: 16px;
}
.about-baxshi .title {
  color: #ce373a;
  font-family: 'Playfair Display', sans-serif !important;
  font-size: 20px !important;
  font-weight: 500 !important;
  font-style: italic !important;
  line-height: 1em !important;
  /* font-family: 'DM Sans' !important; */
}
.about-baxshi .p {
  color: #2d3448;
  font-size: 36px;
  font-weight: bold;
  line-height: 40px;
  margin: 20px 0;
  font-family: 'DM Sans' !important;
}
.about-baxshi .lorem {
  color: #62697c;
  font-size: 16px;
}
/* .about-img {
  width: 407px;
  height: 549px;
  background: #34373d;
} */
.about-img .img-1 {
  width: 407px;
  height: 549px;
  object-fit: cover;
  position: absolute;
  top: 0;
  left: 20px;
  border-radius: 20px 0 20px 0;
}
.about-img .img-2 {
  width: 299px;
  height: 388px;
  position: absolute;
  bottom: 0;
  right: 0;
  padding: 20px;
  background: white;
  border-radius: 20px;
}
.about-img .img-2 img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
.practic {
  background: #2d323d;
  border-radius: 20px 0 20px 0;
  position: absolute;
  bottom: 0;
  right: 0;
}
.practic .title .year {
  font-size: 60px;
  font-weight: bold;
}
.practic .title .year .plus {
  color: #ce373a;
}
.practic .p {
  font-size: 24px;
  font-weight: bold;
  line-height: 26px;
  margin: 20px 0;
}
.practic .lorem {
  font-size: 16px;
}
#about {
  padding: 40px 0;
  position: relative;
  z-index: 1;
}
.item img {
  width: 60px;
  height: 60px;
  object-fit: cover;
  margin-right: 15px;
}
.item .text .title {
  font-weight: bold;
  font-size: 18px;
  font-family: 'DM Sans', sans-serif !important;
}
.item .text p {
  color: gray;
  margin-top: 10px;
}
@media (max-width: 957px) {
  .practic {
    position: inherit;
  }
  .about-footer .bg-2 {
    width: 100%;
    justify-content: center;
  }
}
@media (max-width: 600px) {
  .about-img {
    width: 324px !important;
    height: 464px !important;
  }
  .about-img .img-1 {
    width: 325px !important;
    height: 350px !important;
  }
  .about-img .img-2 {
    width: 258px !important;
    height: 318px !important;
  }
  .person {
    flex-direction: column;
  }
  .person .more {
    margin-top: 40px;
  }
  .person .name {
    margin-top: 20px;
  }
}
</style>

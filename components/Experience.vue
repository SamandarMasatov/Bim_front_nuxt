<template>
    <div>
        <div class="about-footer mt-16">
      <div class="bg"></div>
      <div class="bg-2"></div>
      <img src="/images/home.png" alt="" />
      <v-container>
        <v-row style="position: relative; z-index: 2">
          <v-col cols="11" lg="6" class="about-footer-left mx-auto">
            <div class="footer-title">
              Baxshichilik va san'at maktabida 20 yillik tajriba
            </div>
            <div class="footer-p">
              Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
              eiusmod tempor incididunt ut labore et dolore magna aliqua.
            </div>
            <div class="degres">
              <div class="item">
                <div
                  class="title d-flex align-center justify-space-between"
                  style="width: 89%"
                >
                  <div class="name">Chizma</div>
                  <div class="value">89%</div>
                </div>
                <div class="result">
                  <div class="result-value"></div>
                </div>
              </div>
            </div>
          </v-col>
          <v-col cols="6"></v-col>
        </v-row>
      </v-container>
    </div>
    </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display&display=swap');


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
</style>

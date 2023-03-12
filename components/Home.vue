<template>
  <div id="home">
    <div class="bg">
      <div class="title">
        <v-container>
          <div class="width text">
            <h1>
              Sizning iste'dodingizni rivojlantiradigan
            <span>baxshichilik</span> san'at maktabi
            </h1>
          </div>
          <p class="width py-5">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
            eiusmod tempor incididunt ut labore et dolore magna aliqua Utenimad
            minim veniam, quis nostrud exercitation dolore magna
          </p>
          <v-btn class="get-started py-7 px-10" elevation="0">boshlash</v-btn>
        </v-container>
      </div>
    </div>
    <div class="slider">
      <div class="slide" :style="`left: -${item * 100}vw`">
        <div class="sld">
          <img src="/images/1.jpg" class="img" />
        </div>
        <div class="sld">
          <img src="/images/2.jpg" class="img" />
        </div>
        <div class="sld">
          <img src="/images/3.jpg" class="img" />
        </div>
        <div class="sld">
          <img src="/images/4.jpg" class="img" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      item: 0,
      title: '',
      t: this.setTime(),
    }
  },
  methods: {
    setTime() {
      setInterval(() => {
        this.item++
        if (this.item == 4) {
          this.item = 0
        }
      }, 4000)
    },
  },
}
</script>

<style scoped>
.width {
  max-width: 700px;
}
#home {
  position: relative;
}
.bg {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.664);
  display: flex;
  align-items: center;
  z-index: 1;
}
.bg .title {
  width: 100%;
  color: white;
}
.title .text h1{
  font-size: 60px !important;
  line-height: 75px;
  margin-bottom: 20px;
  font-family: 'DM Sans' !important;
}
.title .text span {
  background: #ce373a;
  font-family: 'Playfair Display', sans-serif !important;
  font-size: 20px !important;
  font-weight: 500 !important;
  font-style: italic !important;
  line-height: 1em !important;
  font-size: 60px !important;
}
.title p {
  font-size: 16px;
  margin-bottom: 20px;
}
.title .get-started {
  border-radius: 15px 0px 15px 0px;
  background: #ce373a;
  color: white;
  font-size: 18px;
}
.slider {
  height: 1000px;
  position: relative;
  left: 0;
  overflow: hidden;
}
.slide {
  width: 400vw;
  height: 1000px;
  position: absolute;
  left: 0;
  top: 0;
  display: flex;
  transition: 1s ease all;
}
.sld {
  height: 1000px;
  width: 25%;
}
.sld .img {
  width: 100%;
  height: 1000px;
  object-fit: cover;
}
@media (max-width: 600px) {
  .title .text h1 {
    font-size: 35px !important;
    line-height: 55px;
  }
  .title .text span {
    font-size: 35px !important;
    line-height: 55px;
  }
}
</style>
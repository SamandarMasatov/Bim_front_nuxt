<template>
  <div class="container" id="kurs">
    <div class="text-center title">
      <h5>Bizning kurslar</h5>
      <h2 class="my-5">Baxshichilik maktabi kurslari bilan tanishing</h2>
      <p>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
        <br />
        tempor incididunt ut labore et dolore magna aliqua
      </p>
    </div>
    <v-card-actions class="button_link">
      <v-btn text color="#ce373a" :to="`/ourclass`" class="button">
        Barcha kurslarni ko'rish
        <v-icon class="kurs-icon">mdi-arrow-right</v-icon></v-btn
      >
    </v-card-actions>
    <v-row class="d-flex flex-wrap class-row">
      <v-col
        cols="12"
        sm="6"
        lg="4"
        data-aos="fade-up"
        v-for="item of clases"
        :key="item.id"
      >
        <v-card class="mx-auto class-card mt-5">
          <v-card-text>
            <v-icon class="icon-class">mdi-pencil-box-multiple</v-icon>
            <p class="text-h5 mt-4">{{ item.title }}</p>
            <p class="text-decaration">
              {{ item.descriptionSmoll }}
            </p>
          </v-card-text>
          <v-card-actions>
            <v-btn text color="#ce373a" :to="`/ourclass`" class="button">
              Kurslarni tanlash
              <v-icon class="kurs-icon">mdi-arrow-right</v-icon></v-btn
            >
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  name: 'OurClass',
  data() {
    return {
      clases: [],
    }
  },

  mounted() {
    this.$axios.get('/cours/getAll').then((res) => {
      this.clases = res.data
    })
  },
}
</script>

<style scoped>
.title {
  margin-top: 100px;
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
p {
  color: #62697c;
  font-size: 16px !important;
}
h2 {
  color: #2d3448;
  font-family: 'DM Sans' !important;
}
.text-h4 {
  color: #2d3448 !important;
}
.class-text2 {
  position: absolute !important;
  top: 25%;
  color: #fff !important;
  left: 0;
  right: 0;
}
.class-btn {
  position: absolute !important;
  z-index: 9 !important;
  left: 0 !important;
  right: 0 !important;
  top: 60% !important;
  transition: 0.5s ease;
  border-top-left-radius: 10px;
  border-bottom-right-radius: 10px;
  border-top-right-radius: 0 !important;
  border-bottom-left-radius: 0 !important;
  width: 210px;
  margin: 0 auto;
}
.class-btn:hover {
  background: #fff !important;
  color: black !important;
  margin-top: -10px !important;
}
.class-row {
  margin-bottom: 100px;
}
.bg-class {
  background: url('/images/3.jpg') !important;
  background-position: center !important;
  background-size: cover !important;
  filter: brightness(0.3) !important;
  height: 100% !important;
  width: 100% !important;
}
.class-card {
  border-top-left-radius: 25px !important;
  border-bottom-right-radius: 25px !important;
  border-top-right-radius: none !important;
  border-bottom-left-radius: none !important;
  position: relative;
  transition: 0.2s;
}
.class-card:hover{
 box-shadow: 15px 15px 30px rgb(0 0 0 / 10%) !important;
}
.class-card1 {
  border-top-left-radius: 25px !important;
  border-bottom-right-radius: 25px !important;
  border-top-right-radius: none !important;
  border-bottom-left-radius: none !important;
  position: relative;
  height: 310px;
  overflow: hidden;
}
.text-class {
  opacity: 0.5;
  width: 550px;
}
.class-text {
  display: flex;
  justify-content: center;
}
.v-card--reveal {
  bottom: 0;
  opacity: 1 !important;
  position: absolute;
  width: 100%;
}
.icon-class {
  font-size: 50px !important;
}
.button_link {
  display: flex;
  justify-content: end;
}
.kurs-icon {
  margin-left: 5px;
}
.button:hover .kurs-icon {
  padding-left: 10px;
}
</style>

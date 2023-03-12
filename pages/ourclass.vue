<template>
  <v-container>
    <Header2 />
    <v-container id="kurs">
      <v-row align="center" class="my-10">
        <p><Nuxt-link to="/">Bosh sahifa</Nuxt-link></p>
        <p class="mx-3">
          <v-icon class="d-block">mdi-arrow-right-thin</v-icon>
        </p>
        <p class="text">Kurslar</p>
      </v-row>
      <v-row align-content="center" justify="space-between">
        <h2 class="">Barcha o‘quv kurslar</h2>
        <div class="courses-name px-3 py-5  d-md-flex d-none">
          <p class="cours_title">Barcha kurslar</p>
          <p v-for="item of clases" :key="item._id" class="mx-3">
            {{ item.title }}
          </p>
        </div>
      </v-row>
      <v-row class="d-flex flex-wrap class-row">
        <v-col
          cols="12"
          data-aos="fade-up"
          v-for="item of clases"
          :key="item.id"
          class="my-5 px-0"
        >
          <v-card class="mx-auto class-card mt-5">
            <v-row class="card-container">
              <v-col cols="12" sm="2" class="card-icon">
                <v-img :src="`http://localhost:3030/uploads/cours/${item.file}`"></v-img>
              </v-col>
              <v-col cols="12" sm="10">
                <v-col>
                  <v-row justify="end" class="d-sm-flex d-block">
                    <p class="mx-4 davomiylik px-2 py-1 mt-1">
                      Davomiyligi: 22 soat
                    </p>
                    <p class="mx-4 dars-soni px-2 py-1 mt-1">Darslar soni: 95 ta</p>
                  </v-row>
                </v-col>

                <v-card-text>
                  <p class="text-h5">{{ item.title }}</p>
                  <p class="text-decaration mt-3">
                    {{ item.descriptionBig }}
                  </p>
                </v-card-text>
              </v-col>
            </v-row>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </v-container>
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
.border {
  border: 1px solid;
}
a {
  text-decoration: none;
  color: #62697c;
}
#kurs {
  margin: 100px auto;
}
.courses-name {
  display: flex;
  align-items: center;
  background-color: #f1f0ee;
  border-radius: 100px;
}
.cours_title {
  background-color: #fff;
  border-radius: 100px;
  padding: 3px 10px;
  font-weight: 700;
  color: #000;
}
h5 {
  color: #ce373a;
  font-size: 20px;
}
h2 {
  font-size: 40px;
}
p {
  color: #62697c;
  margin: 0;
}
h2 {
  color: #2d3448;
}
.text{
    cursor: pointer;
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
  border-radius: 10px !important;
  position: relative;
  transition: 0.2s;
  background-color: #f9f8f7;
  /* box-shadow: none !important; */
}
.class-card:hover {
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
.card-container{
    padding: 20px;
}
.icon-class {
  font-size: 80px !important;
}
.card-icon {
  display: flex;
  align-items: center;
  justify-content: center;
}
.davomiylik {
  border-radius: 100px;
  background-color: #ae8d5e;
  color: #fff;
}
.dars-soni {
  border-radius: 100px;
  background-color: #0eb182;
  color: #fff;
}
</style>

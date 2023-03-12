<template>
  <div>
    <div id="home">
      <!-- <div class="bg">
        <div class="title w-100">
          <v-container class="text-center">
            <div class="width text">
              Sizning iste'dodingizni rivojlantiradigan
              <span>baxshichilik</span> san'at maktabi o'qituvchilari
            </div>
          </v-container>
        </div>
      </div> -->
      <div class="slider">
        <div class="slide">
          <div class="sld">
            <img src="/images/1.jpg" class="img" />
          </div>
        </div>
      </div>
    </div>

    <v-container class="teamSee">
      <v-row justify="center" align="">
        <v-col cols="10" sm="3" md="4">
          <v-card class="mx-auto text-center card">
            <v-img :src="`http://localhost:3030/uploads/team/${teamId.image}`" class="img-fluid"> </v-img>

            <h2 class="mt-16 name">
              {{ teamId.firstName }} {{ teamId.lastName }}
            </h2>

            <v-card-subtitle>{{ teamId.position }}</v-card-subtitle>
            <div class="text-center pb-10">
              <v-btn class="mx-2" outlined fab small color="pink">
                <a href="#"><i class="fa-brands fa-telegram"></i></a>
              </v-btn>

              <v-btn class="mx-2" outlined fab small color="pink">
                <a href="#"><v-icon color="pink"> mdi-instagram </v-icon></a>
              </v-btn>

              <v-btn class="mx-2" outlined fab small color="pink">
                <a href="#"><v-icon color="pink"> mdi-facebook </v-icon></a>
              </v-btn>
            </div>
          </v-card>
        </v-col>
        <v-col cols="10" sm="9" md="8">
          <p>
            {{ teamId.description }}
          </p>
        </v-col>
      </v-row>
      <v-row class="teamSee">
        <v-col
        cols="12"
          sm="6"
          md="4"
          class="teamSee"
          v-for="item of teamNow"
          :key="item"
        >
          <div class="item py-6">
            <v-card class="mx-auto text-center card1">
              <v-img :src="`http://localhost:3030/uploads/team/${item.image}`" class="img-fluid1"> </v-img>

              <h2 class="mt-16 name">
                {{ item.firstName }} {{ item.lastName }}
              </h2>

              <v-card-subtitle>{{ item.position }}</v-card-subtitle>
              <div class="text-center mb-5">
                <v-btn class="mx-2" outlined fab small color="pink">
                  <a href="#"><i class="fa-brands fa-telegram"></i></a>
                </v-btn>

                <v-btn class="mx-2" outlined fab small color="pink">
                  <a href="#"><v-icon color="pink"> mdi-instagram </v-icon></a>
                </v-btn>

                <v-btn class="mx-2" outlined fab small color="pink">
                  <a href="#"><v-icon color="pink"> mdi-facebook </v-icon></a>
                </v-btn>
              </div>
              <Nuxt-link :to="`/TeamSee/${item._id}`">
                <v-btn plain color="pink" class="mb-5">Batafsil</v-btn>
              </Nuxt-link>
            </v-card>
          </div>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>


<script>
export default {
  async asyncData({ params }) {
    const id = await params.id
    return { id }
  },
  data() {
    return {
      teamId: [],
      teamNow: [],
      teams: [],
    }
  },
  mounted() {
    this.$axios.get('/team/getAll').then((res) => {
      this.teams = res.data
      this.teamId = this.teams.find((item) => item._id == this.id)
      this.teamNow = this.teams.filter((item) => item._id != this.id)
    })
  },
}
</script>

<style scoped>
#home {
  position: relative;
}
.border {
  border: 1px solid;
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
  justify-content: center;
  z-index: 1;
}
.bg .title {
  width: 100%;
  color: white;
}
.title .text {
  font-size: 55px;
  line-height: 75px;
  margin-bottom: 20px;
  font-weight: bold;
  font-family: sans-serif;
  text-align: left;
}
.title .text span {
  background: #ce373a;
}
.title .get-started {
  border-radius: 15px 0px 15px 0px;
  background: #ce373a;
  color: white;
  font-size: 18px;
}
.slider {
  width: 100% !important;
  height: 95px;
  position: relative;
  left: 0;
  overflow: hidden;
}
.slide {
  width: 100%;
  position: absolute;
  left: 0;
  top: 0;
  display: flex;
  align-items: center;
  transition: 1s ease all;
}
.sld {
  width: 100%;
  height: 700px;
}
.sld .img {
  width: 100%;
  height: 700px;
  object-fit: cover !important;
}
a {
  text-decoration: none;
}
h5 {
  color: #ce373a;
  font-size: 20px;
}
p {
  color: #62697c;
}
.title p {
  font-size: 16px;
  margin-bottom: 20px;
  color: #fff;
}
h2 {
  color: #2d3448;
}
h2 {
  color: #2d3448;
  font-size: 36px;
  font-family: 'DM Sans', sans-serif !important;
}
.teamSee {
  margin-top: 120px;
}
.name {
  color: #2d3448;
  font-size: 26px;
  font-family: 'DM Sans', sans-serif !important;
}
.card {
  box-shadow: 0 5px 20px 0 rgb(0 0 0 / 5%) !important;
}
.card:hover {
  box-shadow: 0 5px 20px 0 rgb(0 0 0 / 10%) !important;
}
.card1 {
  box-shadow: 0 2px 2px 2px #f0eeeed2 !important;
  position: relative;
  padding-top: 80px;
}
.card1:hover {
  box-shadow: 0 5px 20px 0 rgb(0 0 0 / 10%) !important;
}
.item {
  padding: 0 10px;
}
.img-fluid {
  /* border: 6px solid #f9f9f9; */
  /* height: 186px; */
  object-fit: cover !important;
  overflow: hidden;
  margin: 0 auto;
}
.img-fluid1 {
  position: absolute;
  top: -27% !important;
  left: 0;
  right: 0;
  border: 6px solid #f9f9f9;
  width: 186px;
  height: 186px;
  border-radius: 50% !important;
  object-fit: cover !important;
  overflow: hidden;
  margin: 0 auto;
}
.fa-telegram {
  color: #ce373a;
  font-size: 23px;
}
@media (max-width: 600px) {
  .text {
    font-size: 30px !important;
    line-height: 50px !important;
  }
}
</style>
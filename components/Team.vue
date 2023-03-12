<template>
  <div>
    <v-container>
      <div class="text-center title">
        <h5>Bizning jamoa</h5>
        <h2 class="my-5">Baxshichilik jamoasi azolari</h2>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
          eiusmod
          <br />
          tempor incididunt ut labore et dolore magna aliqua
        </p>
      </div>
      <v-row justify="end" class="mt-16 mb-3" id="controls">
        <button class="button-owl prev">
          <v-icon>mdi-chevron-left</v-icon>
        </button>
        <button class="button-owl next mx-3">
          <v-icon>mdi-chevron-right</v-icon>
        </button>
      </v-row>
      <div class="slide-container">
        <section class="container1" id="slider">
          <div class="thumbnail" v-for="item of teams" :key="item._id">
            <div class="mx-auto text-center card">
              <div class="img-fluid">
                <v-img
                  :src="`http://localhost:3030/uploads/team/${item.image}`"
                  class="img-fluid2"
                >
                </v-img>
              </div>

              <h2 class="mt-10 name">
                {{ item.firstName }} {{ item.lastName }}
              </h2>

              <v-card-subtitle>{{ item.position }}</v-card-subtitle>
              <div class="text-center mb-5">
                <v-btn class="mx-2" outlined fab small color="pink">
                  <a href="#" target="_blank"><i class="fa-brands fa-telegram"></i></a>
                </v-btn>

                <v-btn class="mx-2" outlined fab small color="pink">
                  <a href="#" target="_blank"><v-icon color="pink"> mdi-instagram </v-icon></a>
                </v-btn>

                <v-btn class="mx-2" outlined fab small color="pink">
                  <a href="#" target="_blank"><v-icon color="pink"> mdi-facebook </v-icon></a>
                </v-btn>
              </div>
              <Nuxt-link :to="`/TeamSee/${item._id}`">
                <v-btn plain color="pink" class="mb-5">Batafsil</v-btn>
              </Nuxt-link>
            </div>
          </div>
        </section>
      </div>
    </v-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      teams: [],
    }
  },
  // methods: {
  //   owlPrev() {
  //     owlbutton.trigger('prev.owl.carousel', [300])
  //   },
  //   owlNext() {
  //     owlbutton.trigger('next.owl.carousel', [300])
  //   },
  // },
  mounted() {
    this.$axios.get('/team/getAll').then((res) => {
      this.teams = res.data
    })

    let thumbnail = document.getElementsByClassName('thumbnail')
    let slider = document.querySelector('#slider')
    // let slidecontainer = document.querySelector('.slide-container')
    let prev = document.querySelector('.prev')
    let next = document.querySelector('.next')

    console.log(slider.scrollLeft);

    prev.addEventListener('click', () => {
      slider.scrollLeft -= 385
      console.log('chiqdimi')
    })

    next.addEventListener('click', () => {
      slider.scrollLeft += 385
      console.log('chiqdimi')
    })

    const maxScrollLeft = slider.scrollWidth - slider.clientWidth
    // alert(maxScrollLeft)

    function autoPlay(){
      if(slider.scrollLeft > (maxScrollLeft - 1)){
        slider.scrollLeft -= 385
      }else{
        slider.scrollLeft +=1
      }
    };

    let play = setInterval(autoPlay, 50);

    for (let i = 0; i < thumbnail.length; i++) {
      thumbnail[i].addEventListener('mouseover', () => {
        clearInterval(play)
      })
    }
  },
}
</script>

<style scoped>
a {
  text-decoration: none;
}
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
  /* font-family: 'DM Sans' !important; */
}
p {
  color: #62697c;
  font-size: 16px;
}
h2 {
  color: #2d3448;
  font-size: 36px;
  font-family: 'DM Sans', sans-serif !important;
}
.name {
  color: #2d3448;
  font-size: 26px;
  font-family: 'DM Sans', sans-serif !important;
}
.card {
  margin-top: 120px;
  box-shadow: 0 5px 20px 0 rgb(0 0 0 / 5%) !important;
  padding-top: 80px;
  padding-left: 50px;
  padding-right: 50px;
}
.card:hover {
  box-shadow: 0 5px 20px 0 rgb(0 0 0 / 10%) !important;
}
.item {
  padding: 0 10px;
}
.img-fluid {
  position: relative;
  margin-top: -160px !important;
  border: 6px solid #f9f9f9;
  width: 220px;
  height: 220px;
  border-radius: 50% !important;
  overflow: hidden;
  margin: 0 auto;
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1;
}
.img-fluid2 {
  width: 100%;
  height: 100%;
  object-fit: cover !important;
  transition: 0.5s;
}
.button-owl {
  background-color: #ce373a;
  border-radius: 4px;
}
.button-owl:active {
  box-shadow: 0 0 10px #ce373a;
}
.button-owl i {
  color: #fff;
}
.fa-telegram {
  color: #ce373a;
  font-size: 23px;
}

.slide-container {
  max-width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 0 auto;
}
section {
  width: 100%;
  display: flex;
  justify-content: flex-start;
  align-items: center;
  margin: 0 auto;
  flex-wrap: nowrap;
  overflow-x: auto;
  -webkit-overflow-scrolling: touch;
}
section::-webkit-scrollbar {
  height: 5px;
  width: 2px;
  border: 1px solid #d5d5d5;
  background-color: #d5d5d5;
}
section::-webkit-scrollbar-track {
  --webkit-box-shadow: inset 0 0 6px rgb(0, 0, 0, 0.3);
}
section::-webkit-scrollbar-thumb {
  background-color: #ce373a;
  outline: #d5d5d5;
  border-radius: 100px;
}
.thumbnail {
  flex: 0 0 auto;
  object-fit: cover;
  margin: 32px;
  cursor: pointer;
  transform: scale(0.95);
  transition: 0.3s;
}
.thumbnail:hover {
  transform: scale(1);
}
@media (max-width: 400px) {
  .thumbnail {
    margin: 5px;
  }
}
</style>
<template>
  <div>
    <Header2 />
    <v-container class="News mb-16">
      <v-row align="center" class="my-10">
        <p><Nuxt-link to="/" class="home_link">Bosh sahifa</Nuxt-link></p>
        <p class="mx-3">
          <v-icon class="d-block">mdi-arrow-right-thin</v-icon>
        </p>
        <p class="text1">Yangiliklar</p>
      </v-row>
      <h1 class="text-center mt-16">{{ news.name }}</h1>
      <v-row class="mt-5 justify-center news_card">
       
            <v-col cols="12" sm="9" md="8" class="pa-0">
              <v-img
                class="news-img"
                :src="`http://localhost:3030/uploads/news/${news.image}`"
              ></v-img>
            </v-col>

            <v-col cols="12" sm="9" md="8">
                  <div v-html="news.video" class="d-flex justify-center mt-5"></div>
              <v-row align="center">
                <v-col class="d-flex calendar">
                  <v-icon>mdi-calendar-month-outline</v-icon>
                  <p class="my-3 ms-3">
                    {{ date }}
                  </p>
                </v-col>
              </v-row>
            
              <div class="mb-3 news_text py-2">
                {{ news.description }}
              </div>
            </v-col>
          </v-row>
      <!-- <v-row>
        <v-col cols="12">
          <v-row>
            <v-col cols="3">
              <v-img class="news-img" src="/image/baxshi.jpg"></v-img>
            </v-col>

            <v-col cols="9">
              <v-row align="center">
                <v-col class="d-flex calendar">
                  <v-icon>mdi-calendar-month-outline</v-icon>
                  <p class="my-0 ms-3">08/08/2022</p>
                </v-col>
              </v-row>
              <h3 class="my-3">Baxshilar festivalida rasm lahvalar</h3>

              <div class="mb-3">
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Quaerat
                ipsam recusandae consequatur ratione eos deleniti ipsum itaque
                excepturi corporis accusantium!
              </div>
            </v-col>
          </v-row>
        </v-col>
      </v-row> -->
    </v-container>
  </div>
</template>

<script>
export default {
  name: 'About',
  async asyncData({ params }) {
    const id = await params.id
    return { id }
  },
  data() {
    return {
      news: {}, 
      date: ""
    }
  },

  mounted() {
    this.$axios.get('/news/getAll').then((res) => {
      const d = res.data.find(item => item.slug == this.id)
      this.news = d;
      this.date = d.createdAt.slice(0,10)
    })
  },
}
</script>

<style scoped>
a {
  text-decoration: none;
  color: #62697c;
}
h5 {
  color: #ce373a;
  font-size: 20px;
}
p {
  color: #62697c;
}

h2 {
  color: #2d3448;
  font-size: 40px;
}

.text1 {
  cursor: pointer;
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
.News {
  margin-top: 100px;
}
.news-img {
  object-fit: cover;
  height: 500px;
}
.news_text {
    font-size: 20px;
    line-height: 2;
}
.calendar i {
  color: #ce373a;
}
@media (max-width: 600px) {
  .text {
    font-size: 30px !important;
    line-height: 50px !important;
  }
  .news_card {
    padding: 20px;
  }
  .home_link{
    padding-left: 15px !important;
  }
}
</style>
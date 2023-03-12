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
      <h1 class="text-center mt-16">Yangiliklar bilan batafsil tanishing</h1>
      <v-row class="mt-16">
        <v-col
          cols="12"
          v-for="item of newsmore"
          :key="item._id"
          class="my-5 news_card"
        >
          <v-row>
            <v-col cols="12" sm="4" md="3" class="pa-0">
              <v-img
                class="news-img img-fluid"
                :src="`http://localhost:3030/uploads/news/${item.image}`"
              ></v-img>
            </v-col>

            <v-col cols="12" sm="8" md="9">
              <v-row align="center">
                <v-col class="d-flex calendar">
                  <v-icon>mdi-calendar-month-outline</v-icon>
                  <p class="my-0 ms-3">
                    {{ item.date[0] }}{{ item.date[1] }}{{ item.date[2]
                    }}{{ item.date[3] }}/{{ item.date[5] }}{{ item.date[6] }}/{{
                      item.date[8]
                    }}{{ item.date[9] }}
                  </p>
                </v-col>
              </v-row>
              <h3 class="my-3">{{ item.name }}</h3>

              <div class="mb-3 news_text py-2">
                {{ item.description }}
              </div>
            </v-col>
          </v-row>
          <!-- <v-col cols="12" class="mt-10 px-0">{{ item.description }}</v-col> -->
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
  data() {
    return {
      newsmore: [],
    }
  },

  mounted() {
    this.$axios.get('/news/getAll').then((res) => {
      this.newsmore = res.data
    })
  },
}
</script>

<style>
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
.news_card {
  background-color: #f9f5f5;
  padding: 40px;
}
.News {
  margin-top: 100px;
}
.news-img {
  object-fit: cover;
}
.news_text {
  border-bottom: 2px solid #d5d5d5;
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
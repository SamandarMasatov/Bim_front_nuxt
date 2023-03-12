<template>
  <v-container class="news-wrapper" id="news">
    <h1 class="text-center mb-16">Yangiliklar</h1>
    <div class="button">
      <v-btn to="/NewsMore" text color="#ce373a" class="mb-10 button-link">
        Ko'proq O'qing
        <v-icon>mdi-arrow-right-thin</v-icon></v-btn
      >
    </div>
    <v-row justify="center">
      <v-col cols="12" sm="6" lg="4" v-for="item of news" :key="item._id">
        <v-card class="news-card" aria-multiline="0" outlined>
          <v-img
            class="news-img"
            :src="`http://localhost:3030/uploads/news/${item.image}`"
          ></v-img>
          <v-row align="center" class="mt-3 px-5">
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
          <div class="news_smal">
            <router-link to="/">
              <h3 class="my-3 px-5">{{ item.name }}</h3>
            </router-link>
            <div class="px-5 pb-3">
              <p class="line-clamp">
                {{ item.description }}
              </p>
            </div>
            <div class="button_news_one">
              <v-btn
                :to="`/newsone/${item.slug}`"
                text
                color="#ce373a"
                class="mb-3 button-link"
              >
                Ko'proq O'qing
                <v-icon>mdi-arrow-right-thin</v-icon></v-btn
              >
            </div>
          </div>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'About',
  data() {
    return {
      news: [],
    }
  },

  mounted() {
    this.$axios.get('/news/getAll').then((res) => {
      this.news = res.data.slice(0, 3)
    })
  },
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Arizonia&family=Cormorant+Garamond:wght@600&family=Sacramento&family=Tangerine:wght@700&display=swap');

a {
  text-decoration: none;
}
.news-wrapper {
  margin-top: 100px;
}
.new-btn {
  position: absolute !important;
  top: 5% !important;
  left: 5% !important;
  z-index: 1;
  border-top-left-radius: 10px;
  border-bottom-right-radius: 10px;
  border-top-right-radius: 0 !important;
  border-bottom-left-radius: 0 !important;
  transition: 0.5s ease !important;
}

.new-btn:hover {
  background-color: #fff !important;
  color: black !important;
}
.news-card {
  border: none !important;
  box-shadow: 0 5px 20px 0 rgb(0 0 0 / 0%) !important;
}
.news-card:hover {
  box-shadow: 0 5px 20px 0 rgb(0 0 0 / 10%) !important;
}
.news-img {
  border-top-left-radius: 10px !important;
  border-bottom-right-radius: 0 !important;
  border-bottom-left-radius: 0 !important;
  border-top-right-radius: 10px !important;
  height: 300px;
  object-fit: cover !important;
}
.button {
  display: flex;
  justify-content: end;
}
.button_news_one {
  display: flex;
  justify-content: center;
}
.button-link {
  color: #ce373a !important;
  font-family: 'DM Sans' !important;
  /* border: 1px solid; */
}
h1 {
  font-family: 'Playfair Display', sans-serif !important;
  font-weight: 500 !important;
  font-style: italic !important;
  line-height: 1em !important;
  color: #ce373a;
  font-size: 54px;
}
h3 {
  font-family: 'DM Sans' !important;
  color: #2d3448;
}
p {
  color: #62697c;
}
.calendar i {
  color: #ce373a;
}
</style>

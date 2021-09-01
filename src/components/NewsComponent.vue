<template>
  <section class="news">
    <div class="container">
      <div class="row">
        <div class="col-md-12">
          <h2 class="news__title">Notícias</h2>
        </div>
      </div>
      <div class="row">
        <div
          v-for="(item, index) in newsFiltered"
          :key="item._id"
          :class="{ 'col-md-12': index === 0, 'col-md-6': item._id != 1 }"
        >
          <div class="news__box">
            <img :src="item.img" />
            <h3>{{ item.title }}</h3>
            <p>{{ item.text }}</p>
            <router-link
              class="news__more"
              :to="{ name: 'noticias.detalhe', params: { id: item._id } }"
              ><span>Leia mais</span></router-link
            >
          </div>
        </div>
        <div class="col-md-12" v-if="isButton">
          <router-link class="news__btn" to="/noticias"
            ><button>Veja mais</button></router-link
          >
        </div>
      </div>
    </div>
  </section>
</template>
<script>
export default {
  name: "NewsComponent",
  props: {
    isButton: Boolean,
  },
  data: function () {
    return { news: [] };
  },
  computed: {
    newsFiltered: function () {
      const news = this.news;

      if (this.isButton) {
        return news.slice(0, 3);
      }

      return news;
    },
  },
  methods: {
    getNews: async function () {
      const result = await fetch("http://localhost:3000/noticias")
        .then((res) => res.json())
        .catch((erro) => {
          return {
            erro: true,
            message: erro,
          };
        });
      if (!result.erro) {
        this.news = result;
      }
    },
  },
  created: function () {
    this.getNews();
  },
};
</script>
<style>
.news {
  background-color: #212121;
  padding: 56px 0;
  color: #e2e2e2;
}
.news__title {
  font-size: 36px;
}
.news h3 {
  font-size: 26px;
}
.news p {
  font-size: 16px;
}
.news__more {
  text-decoration: none;
}
.news span {
  color: #7312c3;
  font-size: 14px;
}
.news img {
  width: 100%;
  height: 400px;
  object-fit: cover;
}
.news__box {
  margin-bottom: 30px;
}
.news button {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 200px;
  height: 60px;
  background-color: #e2e2e2;
  color: #212121;
  text-align: center;
  text-decoration: none;
  line-height: 31px;
  margin-top: 10px;
  margin-bottom: 30px;
  border-radius: 6px;
  font-size: 18px;
  font-weight: 600;
  border: 3px solid transparent;
}

.news button:hover {
  border: 3px solid rgba(161, 161, 161, 0.82);
  background-color: rgba(108, 28, 173, 0.342);
  color: #e2e2e2;
  transition: 0.5s ease-in;
}

.news__btn {
  display: block;
  text-align: center;
  margin: 30px auto;
  width: 170px;
  height: 40px;
  text-decoration: none;
}
</style>

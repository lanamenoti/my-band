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
          v-for="item in newsFiltered"
          :key="item.id"
          :class="{ 'col-md-12': item.id === 1, 'col-md-6': item.id != 1 }"
        >
          <div class="news__box">
            <img :src="item.img" />
            <h3>{{ item.titulo }}</h3>
            <p>{{ item.descricao }}</p>
            <router-link
              :to="{ name: 'noticias.detalhe', params: { id: item.id } }"
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
  data: function() {
    return {
      news: [
        {
          id: 1,
          titulo: "Noticia um",
          descricao:
            "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took",
          img: require("../assets/news.jpg"),
        },
        {
          id: 2,
          titulo: "Noticia dois",
          descricao:
            "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took",
          img: require("../assets/news.jpg"),
        },
        {
          id: 3,
          titulo: "Noticia três",
          descricao:
            "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took",
          img: require("../assets/news.jpg"),
        },
        {
          id: 4,
          titulo: "Noticia um",
          descricao:
            "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took",
          img: require("../assets/news.jpg"),
        },
        {
          id: 5,
          titulo: "Noticia dois",
          descricao:
            "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took",
          img: require("../assets/news.jpg"),
        },
        {
          id: 6,
          titulo: "Noticia três",
          descricao:
            "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took",
          img: require("../assets/news.jpg"),
        },
      ],
    }
  },
  computed: {
    newsFiltered: function() {
      const news = this.news

      if (this.isButton) {
        return news.slice(0, 3)
      }

      return news
    },
  },
}
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
.news span {
  color: #c3121c;
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
  width: 170px;
  height: 40px;
  cursor: pointer;
  background: #c3121c;
  color: #212121;
  border-radius: 6px;
  border: none;
  font-weight: bold;
}

.news__btn {
  display: block;
  text-align: center;
  margin: 30px auto;
  width: 170px;
  height: 40px;
}
</style>

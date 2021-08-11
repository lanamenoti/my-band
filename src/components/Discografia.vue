<template>
  <section class="discografia">
    <div class="container">
      <div class="row">
        <div class="col-md-12">
          <h2>Discografia</h2>
        </div>
      </div>
      <div class="row">
        <div v-for="album in albuns" :key="album.name" class="col-md-3">
          <div class="discografia__card">
            <img :src="album.img" :alt="album.name" />
            <h5 v-text="album.name"></h5>
            <a :href="album.link" target="_blank"> Ouvir </a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Discografia",
  data: function () {
    return {
      albuns: [
        {
          name: "Climatizar",
          img: require("../assets/album_1.jpg"),
          link: "https://www.youtube.com/watch?v=eRUa-1kTvT4",
        },
        {
          name: "Chão de estrelas",
          img: require("../assets/album_2.png"),
          link: "https://www.youtube.com/watch?v=B3YHbLnWRg0",
        },
        {
          name: "Prazer, eu sou ferrugem",
          img: require("../assets/album_3.jpg"),
          link: "https://www.youtube.com/watch?v=fVQ3YYnic2o",
        },
        {
          name: "Climatizar",
          img: require("../assets/album_1.jpg"),
          link: "https://www.youtube.com/watch?v=eRUa-1kTvT4",
        },
        {
          name: "Chão de estrelas",
          img: require("../assets/album_2.png"),
          link: "https://www.youtube.com/watch?v=B3YHbLnWRg0",
        },
        {
          name: "Prazer, eu sou ferrugem",
          img: require("../assets/album_3.jpg"),
          link: "https://www.youtube.com/watch?v=fVQ3YYnic2o",
        },
      ],
    };
  },
};
</script>

<style>
.discografia {
  padding: 56px 0;
  background-color: rgba(23, 6, 37, 0.959);
  color: #e2e2e2;
}
.discografia h2 {
  padding-bottom: 30px;
}
.discografia__card {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 340px;
}
.discografia__card img {
  border-radius: 5px;
  box-shadow: 5px 5px 6px 0px rgba(161, 161, 161, 0.82);
  height: 200px;
  width: 200px;
}
.discografia__card a {
  display: block;
  width: 70px;
  height: 30px;
  background-color: #e2e2e2;
  color: #212121;
  text-align: center;
  text-decoration: none;
  line-height: 31px;
  margin-top: 10px;
  margin-bottom: 30px;
  border-radius: 6px;
  font-size: 14px;
  font-weight: 900;
  border: 3px solid transparent;
}
.discografia__card a:hover {
  border: 3px solid rgba(161, 161, 161, 0.82);
  background-color: rgba(108, 28, 173, 0.342);
  color: #e2e2e2;
  transition: 0.5s ease-in;
}
.discografia__card h5 {
  font-size: 16px;
  text-align: center;
  padding: 0px;
  display: inline-block;
  max-width: 150px;
  margin: auto;
}
</style>
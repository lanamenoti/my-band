<template>
  <div class="new-details">
    <Header />
    <section>
      <div class="container">
        <div class="row">
          <div class="col-md-12">
            <h2>{{ newDetail.title }}</h2>
            <img :src="newDetail.img" />
            <p>{{ newDetail.text }}</p>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>
<script>
import Header from "../components/Header.vue";

export default {
  name: "NewsDetail",
  components: {
    Header,
  },
  data: function () {
    return {
      newDetail: {},
    };
  },
  methods: {
    getNewByID: async function () {
      const result = await fetch(
        `http://localhost:3000/noticias/${this.$route.params.id}`
      )
        .then((res) => res.json())
        .catch((error) => {
          return {
            error: true,
            message: error,
          };
        });
      if (!result.error) {
        this.newDetail = result;
      }
    },
  },
  created: function () {
    this.getNewByID();
  },
};
</script>
<style>
.new-details {
  height: 100vh;
  background-color: #212121;
  color: #e2e2e2;
}
.new-details h2 {
  padding-top: 56px;
}
.new-details img {
  margin: 20px auto;
  display: block;
}
</style>

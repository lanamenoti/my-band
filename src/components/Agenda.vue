<template>
  <section class="agenda">
    <div class="container">
      <div>
        <div class="row">
          <div class="col-md-6">
            <h2 class="agenda__title">Agenda</h2>
          </div>
          <div class="col-md-6">
            <input type="text" v-model="search" placeholder="Pesquisar..." />
          </div>
        </div>
      </div>
      <div class="row">
        <div
          class="col-md-4"
          v-for="evento in eventosFiltrados"
          :key="evento.id"
        >
          <Card :titulo="evento.titulo" :descricao="evento.descricao"></Card>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import Card from "./Card.vue"

export default {
  name: "Agenda",
  components: {
    Card,
  },
  data: function() {
    return {
      search: "",
      eventos: [
        {
          id: 1,
          titulo: "Show um",
          descricao:
            "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took",
        },
        {
          id: 2,
          titulo: "Show dois",
          descricao:
            "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took",
        },
        {
          id: 3,
          titulo: "Show tres",
          descricao:
            "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took",
        },
        {
          id: 4,
          titulo: "Show quatro",
          descricao:
            "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took",
        },
        {
          id: 5,
          titulo: "Show cinco",
          descricao:
            "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took",
        },
        {
          id: 6,
          titulo: "Show seis",
          descricao:
            "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took",
        },
      ],
    }
  },
  computed: {
    eventosFiltrados: function() {
      return this.eventos.filter((evento) =>
        evento.titulo.toLowerCase().includes(this.search.toLowerCase())
      )
    },
  },
}
</script>

<style>
.agenda {
  padding: 56px 0px;
  background-color: #e2e2e2;
  width: 100%;
  height: 800px;
}
.agenda .row {
  align-items: flex-start;
}
.agenda .agenda__title {
  font-size: 36px;
  padding: 0;
  margin: 0;
}
.agenda input {
  border-radius: 50px;
  background-color: #f1f1f1;
  border: none;
  width: 70%;
  height: 30px;
  padding: 4px 14px;
  float: right;
}
</style>

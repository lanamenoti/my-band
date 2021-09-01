<template>
  <div class="card">
    <h2 class="card__tittle">{{ titulo }}</h2>
    <p class="card__description">{{ descricao }}</p>
    <b-button variant="outline-secondary">Detalhe</b-button>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: {
    titulo: String,
    descricao: String,
  },
};
</script>

<style>
.card {
  background: #fafafa;
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
  padding: 30px;
  margin: 20px 10px;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.card .card__tittle {
  font-size: 18px;
  font-weight: bold;
  color: #000000;
}
.card .card__description {
  font-size: 14px;
  color: #000000;
}
</style>

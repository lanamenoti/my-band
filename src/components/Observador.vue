<template>
  <div class="observador">
    <input type="text" v-model="nome" />
    <p>{{message}}</p>
  </div>
</template>
<script>
export default {
  name: "Observador",
  data: function () {
    return {
      nome: "",
      message: ""
    };
  },
  watch: {
      nome: function() {
          this.message = "Campo alterado"
      }
  }
};
</script>
<style>
.observador {
    padding: 50px;
}
</style>
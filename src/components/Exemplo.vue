<template>
  <div>
      <button @click="toShow">toggle</button>
      <div v-show="haveToShow">
        <p v-text="texto"></p>
      </div>
  </div>
</template>

<script>
export default {
    name: "Exemplo",
    data: function() {
        return {
            texto: "Aqui vai texto",
            haveToShow : true
        }
    },
    methods: {
        toShow : function() {
            this.haveToShow = !this.haveToShow
        }
    }
}
</script>

<style>

</style>
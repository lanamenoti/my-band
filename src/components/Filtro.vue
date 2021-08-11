<template>
  <div class="filtro">
    <input type="text" v-model="searchItem">
    <ul>
      <li v-for="item in itensFiltered" :key="item">
        {{ item }}
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: "Filtro",
  data: function () {
    return {
      searchItem: "",
      items: ["Brasil", "Argentina", "Paraguai", "Uruguai"],
    };
  },
  computed: {
      itensFiltered: function() {
          return this.items.filter(item => item.toLowerCase().includes(this.searchItem.toLowerCase()))
      }
  }
};
</script>
<style>
.filtro {
  padding: 30px;
}
</style>
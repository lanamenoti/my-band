<template>
  <nav class="menu">
    <ul>
      <li><router-link to="/">Home</router-link></li>
      <li>Biografia</li>
      <li><router-link to="/noticias">Notícias</router-link></li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: "Menu",
}
</script>

<style>
.menu ul {
  list-style: none;
  padding: 0;
  margin: 0;
  color: #e2e2e2;
  display: flex;
  flex-direction: row;
  width: 100%;
  align-items: center;
}

.menu ul li {
  padding: 4px 14px;
  font-size: 16px;
  text-transform: uppercase;
  font-weight: 900;
  letter-spacing: 0.5px;
}

.menu ul li:not(:last-child):after {
  content: "";
  display: inline-block;
  width: 1px;
  background-color: #e2e2e2;
  height: 10px;
  margin-left: 10px;
}

.menu ul li:hover {
  background-color: #333;
}
</style>

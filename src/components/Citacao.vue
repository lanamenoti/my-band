<template>
  <section class="citacao">
    <div class="container">
      <div class="row">
        <div class="col-md-12">
          <p class="citacao__text">
            “Lorem Ipsum is simply dummy text of the printing and typesetting
            industry. Lorem Ipsum has been the industry's standard dummy text
            ever since the 1500s, when an unknown printer took a galley of type
            and scrambled it to make a type specimen book. “
          </p>
          <p class="citacao__author">(Mano Bronw)</p>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
export default {
  name: "Citacao",
};
</script>
<style>
.citacao {
  background-color: rgba(161, 161, 161, 0.82);
  width: 100%;
  height: 255px;
  padding-top: 70px;
}
.citacao .citacao__text {
  color: rgba(42, 17, 63, 0.986);
  font-size: 20px;
  font-style: italic;
}
.citacao .citacao__author {
  color: rgba(54, 13, 87, 0.76);
  font-size: 16px;
  text-align: right;
}
</style>
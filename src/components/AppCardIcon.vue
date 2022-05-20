<template>
  <div class="col mt-5">
      <div class="element-card">
          <div class="card-image">
              <img :src="cardObj.poster" :alt="cardObj.title"/>
          </div>
          <h4 class="text-uppercase fw-bold mt-5 text-center">{{ cardObj.title }}</h4>
          <div class="card-info text-center">
              <div>{{ cardObj.author }}</div>
              <div>{{ cardObj.year }}</div>
          </div>
      </div>
  </div>
</template>

<script>
export default {
    name: "AppCardIcon",
    props: ["cardObj"],
}
</script>

<style lang="scss" scoped>
@import "../style/variables.scss";

.element-card {
    width: 150px;
    height: 300px;
    background-color: $brand-primary-color;
}

.card-image {
    width: 120px;
    height: 120px;
    margin: auto;
    padding: 1.5rem 0;
}

h4 {
    font-size: 1rem;
    color: white;
}

.card-info {
    color: gray;
    font-size: .7rem
}

</style>
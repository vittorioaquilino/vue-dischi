<template>
  <section class="ms_header">
      <img src="../assets/img/logo.png" alt="">
  </section>
</template>

<script>
export default {
    name: "AppHeader",
}
</script>

<style lang="scss" scoped>
@import "../style/variables.scss";

.ms_header {
    width: 100%;
    height: 50px;
    background-color: $brand-primary-color;
    display: flex;
    align-items: center;

    img {
        width: 40px;
        margin-left: 1rem;
    }
}
</style>
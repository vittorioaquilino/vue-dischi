<template>
  <section class="filter-card py-3">
      <select 
      v-model="checkedSearch"
      @change="$emit('checkedCard', checkedSearch)"
      >
      <option value="all">tutti</option>
      <option value="rock">rock</option>
      <option value="jazz">jazz</option>
      <option value="pop">pop</option>
      
      </select>
  </section>
</template>

<script>
export default {
    name: "AppFilterCard",
    data: function () {
        return {
            checkedSearch: "all",
        }
    }
}
</script>

<style lang="scss" scoped>
@import "../style/variables.scss";

.filter-card {
    display: flex;
    justify-content: center;
    margin: auto;
}

select {
    width: 30%;
    border-radius: 2rem;
    height: 40px;
}

</style>
<template>
    <div id="app">
       <AppHeader />

          <main>
            <AppContainerList />
          </main>
   
    </div>
</template>

<script>
import AppHeader from "./components/AppHeader.vue";
import AppContainerList from "./components/AppContainerList.vue";

export default {
  name: 'App',
  components: {
    AppHeader,
    AppContainerList,
  }
}
</script>

<style lang="scss">
@import "./style/common.scss";
</style>

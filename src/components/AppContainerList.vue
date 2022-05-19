<template>
    <section class="ms_container">
        <div class="container">
            <div class="container-fluid">
                <div class="row row-cols-5">
                    <AppCardIcon
                    v-for="(element, index) in cardsArray"
                    :key="index"
                    :cardObj="element"
                    />
                </div>
            </div>
      </div>   
    </section>
</template>

<script>
import axios from "axios";
import AppCardIcon from "./AppCardIcon.vue";

export default {
    name: "AppContainerList",
    data: function () {
        return {
            cardsArray: [],
        }
    },
    components: {
        AppCardIcon,
    },
    created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((resp) => {
        this.cardsArray = resp.data.response;
      });
  },
}
</script>

<style lang="scss" scoped>
@import "../style/variables.scss";

.ms_container {
    background-color: $brand-secondary-color;
    width: 100%;
}
.container-fluid {
    width: 65%;
}

</style>
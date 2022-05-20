<template>
    <section class="ms_container">
        <AppFilterCard @checkedCard="filterCard($event)"/>
        <div class="container">
            <div class="container-fluid">
                <div class="row row-cols-5">
                    <AppCardIcon
                    v-for="(element, index) in filterArray"
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
import AppFilterCard from "./AppFilterCard.vue";

export default {
    name: "AppContainerList",
    data: function () {
        return {
            cardsArray: [],
            genre: "all",
        }
    },
    components: {
        AppCardIcon,
        AppFilterCard,
    },
    created() {
        axios
            .get("https://flynn.boolean.careers/exercises/api/array/music")
            .then((resp) => {
                this.cardsArray = resp.data.response;
            });
    },
    methods: {
        filterCard(event) {
            this.genre = event;
            console.log(this.genre);
        }
    },
    computed: {
        filterArray() {
            if (this.genre !== 'all') {
                return  this.cardsArray.filter((element) => {
                return element.genre.toLowerCase() === this.genre;
            });
            } 
        return this.cardsArray
        },
    },
}
</script>

<style lang="scss" scoped>
@import "../style/variables.scss";

.ms_container {
    background-color: $brand-secondary-color;
    width: 100%;
    height: 100vh;
}
.container-fluid {
    width: 65%;
}

</style>
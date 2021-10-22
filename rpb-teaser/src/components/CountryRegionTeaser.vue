<template>
  <div class="teaser">
    <div class="teaser__heading">
      <h1 class="heading">Länder, Regionen, Orte</h1>
      <router-link to=/reiseziele class="link">Alle</router-link>
    </div>

    <h2 class="teaser__subheading">Lorem Ipsum Länder, Regionen, Orte</h2>
    <div class="teaser__slider">
      <Slider :traveloptions="pictures" />
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import { traveloptions } from "../travel-options";
import Slider from "./Slider.vue";

@Component({
  components: {
    Slider,
  },
})
export default class CountryRegionTeaser extends Vue {
  pictures: { text: string; price: number; image: string; link: string }[] = [
    ...traveloptions,
  ];
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "src/assets/global.scss";
@import "src/assets/colors.scss";

.teaser {
  &__heading {
    display: flex;
    align-items: baseline;

    .heading{
      font-family: Quicksand;
      font-weight: bold;
      color: $text-color1;

    }

    .link{
      text-decoration: none;
      font-family: Open Sans;
      color: $text-color1;
      text-align: right;
      margin-left: 10%;
    }
  }

  &__subheading{
      color: $text-color2;
      font-family: Open Sans;
    }
}
</style>

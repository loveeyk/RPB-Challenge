<template>
  <div class="teaser">
    <div class="teaser__heading">
      <h1>Länder, Regionen, Orte</h1>
      <span>Alle</span>
    </div>

    <h2>Lorem Ipsum Länder, Regionen, Orte</h2>
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
export default class Teaser extends Vue {
  pictures: { text: string; price: number; image: string; link: string }[] = [
    ...traveloptions,
  ];
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.teaser {
  &__heading {
    display: flex;
    align-items: baseline;
  }
}
</style>

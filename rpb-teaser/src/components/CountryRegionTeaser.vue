<template>
<div>
  <div class="teaser">
    <div class="teaser__heading">
      <h1 class="heading">Länder, Regionen, Orte</h1>
      <router-link to=/reiseziele class="link">Alle</router-link>
    </div>

    <p class="teaser__subheading">Lorem Ipsum Länder, Regionen, Orte</p>
    
  </div>
  <div class="teaser__slider">
      <Slider />
    </div>
    </div>
</template>

<script lang="ts">
import { Component, Vue} from "vue-property-decorator";
import Slider from "./Slider.vue";

@Component({
  components: {
    Slider,
    
  },
})
export default class CountryRegionTeaser extends Vue {
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "src/assets/global.scss";
@import "src/assets/colors.scss";

.teaser {
  padding-left: 23px;
  margin-bottom: 25px;
  padding: 1rem 1.4rem;

  &__heading {
    display: flex;
    align-items: baseline;

    .heading{
      font-family: Quicksand;
      color: $text-color1;
      font-size: 1.5rem;

    }

    .link{
      text-decoration: none;
      font-family: Open Sans;
      color: $text-color1;
      text-align: right;
      margin-left: 10%;
      font-size: 1rem;
    }
  }
  &__slider::before {
    content: "";
    position: fixed;
    background: linear-gradient(273deg, #ffffff, #ffffff00);
    height: 222px;
    right: 0px;
    z-index: 1;
    width: 23px;
    top: 28%;
  }
    &__slider{
      padding-left: 1.4rem;
      position: relative;
      overflow-y: hidden;
    }
     

  &__subheading{
      color: $text-color2;
      font-family: 'Open Sans';
      font-size: 1rem;
    }
}
</style>

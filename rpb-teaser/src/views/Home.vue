<template>
  <div class="home">
    <div class="home__wrapper">
      <h1>Willkommen auf der <span class="highlight">Restplatzbörse</span></h1>
      <p class="description">
        Gelangen Sie nur mit einem Klick zu unseren aktuellen beliebten
        Reisezielen.
      </p>
      <HeroBtn to="/reiseziele" />
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import HeroBtn from "../components/HeroBtn.vue";

@Component({
  components: { HeroBtn },
})
export default class Home extends Vue {}
</script>
<style scoped lang="scss">
@import "src/assets/global.scss";
@import "src/assets/colors.scss";

.home {
  text-align: center;
  font-family: Open Sans;
  background: url("../assets/img/home-bg.jpg") 100% no-repeat;
  background-size: cover;
  background-position: 50% 50%;
  background-attachment: fixed;
  color: $accent-1;
  display: flex;
  align-items: center;
  flex-direction: column;
  justify-content: center;
  height: 100vh;

  @media only screen and (min-width: 320px) and (max-width: 480px) {
    background: url("../assets/img/home-bg.jpg") no-repeat center center fixed;
  }

  &__wrapper {
    // background: $accent-1;
    color: #525252;
    border: 1px solid transparent;
    width: 350px;
    height: 350px;
    border: 1px solid transparent;
    border-radius: 5px;
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-flow: column wrap;

    h1,
    .description,
    .link {
      position: relative;
      z-index: 2;
    }

    .description {
      padding-bottom: 1rem;
    }

    .link {
      text-decoration: none;
      border: 1px solid transparent;
      padding: 1rem;
      border-radius: 4rem;
      color: $text-color2;
      box-shadow: -2px 2px 0 $text-color1;
      font-size: x-large;
      background-color: $accent-1;
    }
    &::after {
      content: "";
      background: #ffffffad;
      position: absolute;
      top: 0;
      left: 0;
      height: 100%;
      width: 100%;
      -webkit-backdrop-filter: blur(5px);
      backdrop-filter: blur(10px);
    }
  }
}
</style>

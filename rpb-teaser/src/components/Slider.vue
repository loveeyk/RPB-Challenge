<template>
  <div class="slider">
    <div v-if="isMobile">
      <carousel-3d
        :border="0"
        :height="222"
        :width="287"
        :disable3d="true"
        :space="300"
        :clickable="false"
        :controls-visible="true"
        :display="pictures.length"
        :perspective="50"
      >
        <slide
          v-for="(slide, i) in pictures"
          :index="i"
          :key="i"
          class="slider__wrapper"
        >
          <template
            :slot-scope="`${(index, isCurrent, leftIndex, rightIndex)}`"
          >
            <Slideinner :slide="slide"></Slideinner>
          </template>
        </slide>
      </carousel-3d>
    </div>
    <div v-else class="grid">
      <div v-for="(slide, i) in pictures" :index="i" :key="i" class="grid-item">
        <a :href="slide.link" class="link">
          <img :src="slide.image" class="grid__image" :alt="slide.image" />

          <div class="grid__description">
            <span class="countryName">{{ slide.text }}</span>
            <div v-if="slide.price > 0">
              <span class="textcolor">ab</span>
              <span class="pricecolor">€{{ slide.price }}</span>
            </div>
          </div></a
        >
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import { Carousel3d, Slide } from "vue-carousel-3d";
import { traveloptions } from "../travel-options";
import Slideinner from "./Slideinner.vue";

Vue.use(Carousel3d);

@Component({
  components: {
    Slide,
    Carousel3d,
    Slideinner,
  },
})
export default class Slider extends Vue {
  pictures: { text: string; price: number; image: string; link: string }[] = [
    ...traveloptions,
  ];
  isMobile = false;

  setIsMobile() {
    console.log("setIsMobile() wird ausgeführt" + window.innerWidth);
    this.isMobile = window.innerWidth < 769;
  }
  mounted() {
    this.setIsMobile();
    window.addEventListener("resize", this.setIsMobile);
  }

  beforeDestroy() {
    window.removeEventListener("resize", this.setIsMobile);
  }
}
</script>
<style lang="scss" scoped>
@import "src/assets/global.scss";
@import "src/assets/colors.scss";
.carousel-3d-container {
  overflow: unset !important;
}

.slider {
  height: 100vh;

  &__wrapper {
    border: 1px solid transparent;
    box-shadow: -2pt 2pt $border-color;
    border-radius: 10px;
    background: $accent-1;
    height: 222px;
    width: 287px;
  }

  .grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: 1fr 1fr;
    grid-gap: 23px;
    width: 287px;
    padding-left: 1.4rem;

    &__image {
      width: 287px;
      height: 177px;
      border: 1px solid transparent;
      border-top-left-radius: 10px;
      border-top-right-radius: 10px;
    }

    &__description {
      display: flex;
      justify-content: space-between;
      padding: 1rem 1rem;

      .countryName {
        color: $text-color1;
        font-family: "Open Sans";
        font-size: 1rem;
        font-weight: 700;
      }

      .pricecolor {
        color: $text-color3;
        font-size: 1rem;
        font-family: "Open Sans";
        font-weight: 600;
      }

      .textcolor {
        color: $text-color3;
        font-size: 0.75rem;
        font-family: Open Sans;
        margin-right: 10px;
      }
    }

    .grid-item {
      border: 1px solid transparent;
      box-shadow: -2pt 2pt $border-color;
      border-radius: 10px;
      background: $accent-1;

      .link {
        text-decoration: none;
      }
    }
  }
}
</style>

<template>
  <div class="slider">
    <div class="slider__wrapper" v-for="(option, i) in traveloptions" :key="i">
      <a :href="option.link" class="slider__link">
        <img
          :src="option.image"
          :alt="`slider-image-${i}`"
          :id="`slider-image-${i}`"
        />
        <div class="slider__description">
          <span class="slider__text">{{ option.text }}</span>
          <span class="slider__price">ab {{ option.price }}</span>
        </div></a
      >
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue, Prop } from "vue-property-decorator";

@Component
export default class Slider extends Vue {
  @Prop({ type: Array, required: true }) readonly traveloptions!: {
    text: string;
    price: number;
    image: string;
    link: string;
  }[];
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "src/assets/global.scss";
@import "src/assets/colors.scss";
.slider {
  display: flex;
  overflow-y: hidden;

  &__link {
    text-decoration: none;
  }

  &__wrapper {
    border: 1px solid $border-color;
    box-shadow: -1pt 1pt 0 0 $border-color;
    border-radius: 10px;
    margin: 1rem;

    img {
      border: 1px solid $border-color;
      border-top-left-radius: 10px;
      border-top-right-radius: 10px;
    }
  }

  &__description {
    display: flex;
    justify-content: space-between;
    padding: 1rem;
  }
  &__text {
    color: $text-color1;
    font-family: Open Sans;
    font-weight: bold;
  }

  &__price {
    color: $text-color3;
    font-family: Open Sans;
    font-weight: bold;
  }
}
</style>

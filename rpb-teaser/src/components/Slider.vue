<template>
  <div>
    <div class="slider">
      <div
        class="slider__wrapper"
        v-for="(option, i) in pictures"
        :key="i"
        v-bind="traveloptions"
      >
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
    <button @click="left" class="button button-left">
      <img src="../assets/img/left.svg" alt="left" />
    </button>
    <button @click="right" class="button button-right">
      <img src="../assets/img/right.svg" alt="right" />
    </button>
  </div>
</template>

<script lang="ts">
import { Component, Vue, Prop } from "vue-property-decorator";
import { traveloptions } from "../travel-options";

@Component
export default class Slider extends Vue {
  @Prop({ type: Array, required: true }) readonly traveloptions!: {
    text: string;
    price: number;
    image: string;
    link: string;
  }[];

  pictures = [...traveloptions];

  left = () => {
    let tmp = this.pictures.shift();
    this.pictures.push(tmp);
    this.pictures.forEach((option) => console.log(option.text));
    this.$forceUpdate();
  };
  right = () => {
    let tmp = this.pictures.pop();
    this.pictures.unshift(tmp);
  };
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "src/assets/global.scss";
@import "src/assets/colors.scss";
.slider {
  display: flex;
  overflow-y: hidden;
  position: relative;
  -ms-overflow-style: none; /* IE and Edge */
  scrollbar-width: none;

  &::-webkit-scrollbar {
    display: none;
  }

  &__link {
    text-decoration: none;
  }

  &__wrapper {
    border: 2px solid transparent;
    box-shadow: -2px 2px 0 $border-color;
    border-radius: 25px;
    margin: 0 19px;
    height: 222px;

    &:first-child {
      margin-left: 0;
    }
    img {
      border: 1px solid $border-color;
      border-top-left-radius: 10px;
      border-top-right-radius: 10px;
      width: 287px;
      height: 177px;
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
.button {
  position: absolute;
  top: 50%;
  z-index: 10;
  background: transparent;
  border-radius: 5px;
  border: 1px solid transparent;
  &-left {
    left: 0;
  }
  &-right {
    right: 0;
  }
}
</style>

<template>
  <div class="_slide">
    <a :href="slide.link" class="link">
      <img :src="slide.image" class="_slide__image" :alt="slide.image" />
      <div class="_slide__description">
        <span class="countryName">{{ slide.text }}</span>
        <div class="_slide__description-price" v-if="slide.price > 0">
          <span class="textcolor">ab</span>
          <span class="pricecolor">€{{ slide.price }}</span>
        </div>
      </div></a
    >
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";

export default {
  components: {},
  props: {
    slide: Object,
  },
};
</script>

<style scoped lang="scss">
@import "src/assets/global.scss";
@import "src/assets/colors.scss";
._slide {
  .link {
    text-decoration: none;
  }
  &__image {
    width: 287px;
    height: 177px;
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
}
</style>

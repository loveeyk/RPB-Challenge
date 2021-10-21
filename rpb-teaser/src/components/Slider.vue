<template>
  <div class="slider">
    <template class="slider__wrapper" v-for="(option, i) in traveloptions">
      <img
        :src="option.image"
        :alt="`slider-image-${i}`"
        :id="`slider-image-${i}`"
        :key="i"
      />
    </template>
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
.slider {
  display: flex;

  &__wrapper {
    border: 3px solid black;
  }
}
</style>

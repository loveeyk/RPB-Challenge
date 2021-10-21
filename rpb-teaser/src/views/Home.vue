<template>
  <div class="home">
    <Teaser />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import Teaser from "../components/Teaser.vue";

@Component({
  components: {
    Teaser,
  },
})
export default class Home extends Vue {}
</script>

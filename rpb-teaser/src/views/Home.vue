<template>
  <div class="home">
    <CountryRegionTeaser />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import CountryRegionTeaser from "../components/CountryRegionTeaser.vue";

@Component({
  components: {
    CountryRegionTeaser,
  },
})
export default class Home extends Vue {}
</script>
<style scoped lang="scss">
.home {
}
</style>

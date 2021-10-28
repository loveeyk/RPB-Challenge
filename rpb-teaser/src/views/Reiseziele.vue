<template>
  <div class="reiseziele">
    <CountryRegionTeaser :traveloptions="traveloptions" />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import { traveloptions } from "../travel-options";

import CountryRegionTeaser from "../components/CountryRegionTeaser.vue";

@Component({
  components: {
    CountryRegionTeaser,
  },
})
export default class Reiseziele extends Vue {
  traveloptions = [...traveloptions];
}
</script>
<style scoped lang="scss"></style>

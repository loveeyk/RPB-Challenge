<template>
  <div id="app">
    <Navbar />
    <router-view class="wrapper" />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";

import Navbar from "./components/Navbar.vue";

@Component({
  components: {
    Navbar,
  },
})
export default class App extends Vue {}
</script>
<style lang="scss">
@import "src/assets/global.scss";
#app {
  overflow-y: hidden;

  .wrapper {
    margin-top: 68px;
  }
}
</style>

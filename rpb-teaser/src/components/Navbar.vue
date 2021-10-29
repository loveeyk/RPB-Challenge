<template>
  <ul class="navbar">
    <li>
      <router-link to="/" class="navbar-link"
        ><img
          src="../assets/img/logo.svg"
          alt="flight_logo"
          class="logo"
        />Restplatzboerse</router-link
      >
    </li>
    <li class="navbar-list">
      <router-link to="/reiseziele" class="navbar-link">Reiseziele</router-link>
    </li>
  </ul>
</template>

<script lang="ts">
import { Vue } from "vue-property-decorator";

export default class Navbar extends Vue {}
</script>

<style scoped lang="scss">
@import "src/assets/global.scss";
@import "src/assets/colors.scss";
.navbar {
  display: flex;
  justify-content: space-between;
  list-style: none;
  padding: 1rem;
  border-bottom: 1px solid rgba(112, 109, 109, 0.445);
  box-shadow: 0 0.2rem 0.5rem rgb(51 51 51 / 30%);
  width: 100%;
  font-family: Quicksand;

  &-list {
    margin-top: 0.5rem;
  }

  &-link {
    color: $text-color1;
    text-decoration: none;
  }
}
</style>

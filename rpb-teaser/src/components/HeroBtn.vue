<template>
  <button class="hero-btn">
    <svg width="180px" height="60px" viewBox="0 0 180 60" class="border">
      <polyline points="179,1 179,59 1,59 1,1 179,1" class="bg-line"></polyline>
      <polyline points="179,1 179,59 1,59 1,1 179,1" class="hl-line"></polyline>
    </svg>
    <span>
      <router-link :to="to" class="link">{{ text }}</router-link>
    </span>
  </button>
</template>

<script lang="ts">
export default {
  data() {
    return {
      text: "Zu allen Reisezielen",
    };
  },
  props: { to: String },
};
</script>

<style lang="scss" scoped>
@import "src/assets/global.scss";
@import "src/assets/colors.scss";
.link {
  position: relative;
  z-index: 2;
  color: $text-color1;
  text-decoration: none;
}

.hero-btn {
  cursor: pointer;
  background: transparent;
  border: 1px solid rgba(255, 255, 255, 0.116);
  outline: none;
  transition: 1s all ease-in-out;
  position: relative;
  z-index: 2;
  border-radius: 4rem;
  margin-left: -0.9rem;

  span {
    position: relative;
    z-index: 2;
    color: white;
    font-size: 18px;
    font-weight: 100;
    transition: 0.3s all ease-in-out;
    top: 77%;
    left: 4%;
  }

  svg {
    position: absolute;
    z-index: 2;
    left: 0;
    top: 0;
    fill: none;
    stroke: #47eed8;
    stroke-dasharray: 150 480;
    stroke-dashoffset: 150;
    transition: 0.5s all ease-in-out;
    background: $accent-1;
    border-radius: 10px;
  }
}

.hero-btn:hover {
  background: rgba(255, 255, 255, 0.082);
}
.hero-btn:hover svg {
  stroke-dashoffset: -480;
}
.hero-btn:hover span {
  color: #47eed8;
}
</style>

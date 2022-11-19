<script>
export default {
  name: "HeaderNav",
  props: {
    NavItems: Object,
  },
};
</script>

<template>
  <li>
    <a :href="NavItems.link">{{ NavItems.name }}</a>
  </li>
</template>
<style lang="scss" scoped>
@use "../styles/partials/variables" as *;

li {
  text-transform: uppercase;
  color: $naturalGrey;
  font-weight: bold;
  font-size: 0.7rem;
  position: relative;

  &:hover {
    color: $scarlet;
  }

  &:after {
    content: " ";
    background-color: $scarlet;
    width: 100%;
    position: absolute;
    height: 0px;
    bottom: -10px;
    left: 0;
    z-index: 999;
    display: inline-block;
  }

  &:hover::after {
    animation: grow-border 500ms;
    height: 5px;
  }

  @keyframes grow-border {
    0% {
      height: 0;
    }
    100% {
      height: 5px;
    }
  }
}
</style>

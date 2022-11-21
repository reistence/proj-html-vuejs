<script>
export default {
  name: "FooterNewsItem",
  props: {
    newsItem: Object,
  },
};
</script>

<template>
  <li class="newsitem">
    <span><i class="fa-solid fa-chevron-right"></i></span>
    <a :href="newsItem.link">{{ newsItem.title }}</a>
  </li>
</template>

<style lang="scss" scoped>
.newsitem {
  margin-bottom: 1.5em;
  font-size: 0.7rem;
  font-weight: 200;
  margin-left: 1em;
  span {
    font-size: 0.6rem;
    margin-right: 0.6em;
  }

  &:hover {
    color: white;
    transition: 300ms;
  }
}
</style>

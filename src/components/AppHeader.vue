<script>
export default {
  name: "AppHeader",
  data() {
    return {
      navHeaderList: [
        "home",
        "pages",
        "program",
        "tickets",
        "speakers",
        "papers",
        "blog",
        "shortcodes",
      ],
    };
  },
};
</script>
<template>
  <header>
    <div class="container">
      <div class="logo">
        <img src="../assets/images/logo.png" alt="The Keynote" />
      </div>
      <nav>
        <ul>
          <li v-for="(item, index) in navHeaderList" :key="index">
            {{ item }}
          </li>
          |
          <li class="lens">
            <i class="fa-solid fa-magnifying-glass"></i>
          </li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<style lang="scss" scoped>
@use "../styles/partials/variables" as *;

header {
  .container {
    padding: 2em 0;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;

    .logo {
      width: 30%;
      img {
        width: 60%;
      }
    }

    nav {
      width: 70%;
    }

    ul {
      display: flex;
      flex-direction: row;
      flex-wrap: wrap;
      justify-content: space-between;
      align-items: center;
      gap: 1em;

      li {
        text-transform: uppercase;
        color: $naturalGrey;
        font-weight: bold;
        font-size: 0.9rem;
        position: relative;
        i {
          font-size: 1rem;
        }

        &:after {
          content: " ";
          color: $scarlet;
          width: 100%;
          position: absolute;
          height: 4px;
          bottom: -10px;
          left: 0;
          z-index: 999;
        }
      }
    }
  }
}
</style>

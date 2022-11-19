<script>
import HeaderNav from "./HeaderNav.vue";
export default {
  name: "AppHeader",
  components: {
    HeaderNav,
  },
  data() {
    return {
      navHeaderList: [
        {
          name: "home",
          link: "/home",
        },
        {
          name: "pages",
          link: "/pages",
        },
        {
          name: "program",
          link: "/programs",
        },
        {
          name: "tickets",
          link: "/tickets",
        },
        {
          name: "speakers",
          link: "/speakers",
        },
        {
          name: "papers",
          link: "/papers",
        },
        {
          name: "blog",
          link: "/blog",
        },
        {
          name: "shortcodes",
          link: "/shortcodes",
        },
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
          <HeaderNav
            v-for="(item, index) in navHeaderList"
            :key="index"
            :NavItems="item"
          >
          </HeaderNav>
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
      flex-wrap: nowrap;
      justify-content: space-between;
      align-items: center;
      gap: 1em;
      color: $gray;

      li {
        position: relative;
        cursor: pointer;
      }
      i {
        font-size: 1rem;
        color: $gray;
      }

      // li:last-child {
      //   &:hover {
      //     color: $scarlet;
      //   }

      //   &:after {
      //     content: " ";
      //     background-color: $scarlet;
      //     width: 100%;
      //     position: absolute;
      //     height: 0px;
      //     bottom: -10px;
      //     left: 0;
      //     z-index: 999;
      //     display: inline-block;
      //   }

      //   &:hover::after {
      //     height: 5px;
      //   }
      // }
    }
  }
}
</style>

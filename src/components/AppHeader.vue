<script>
import { onMounted } from "vue";
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
      scrollPosition: null,
    };
  },
  methods: {
    updateScroll() {
      this.scrollPosition = window.scrollY;
    },
  },
  mounted() {
    window.addEventListener("scroll", this.updateScroll);
  },
};
</script>
<template>
  <header :class="{ faded: scrollPosition > 50 }">
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
  position: fixed;
  height: 70px;
  top: 0;
  left: 0;
  z-index: 999;
  background-color: $white;
  width: 100%;

  &.faded {
    background-color: rgba(255, 255, 255, 0.594);
    transition: 500ms;
    backdrop-filter: blur(10px);

    box-shadow: 1px 1px 5px rgb(192, 191, 191);
    &:hover {
      background-color: $white;
      filter: blur(0);
    }
  }
  .container {
    padding: 2em 0;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    height: 70px;

    .logo {
      width: 30%;
      transition: 500ms;
      cursor: pointer;
      &:hover {
        transform: scale(1.1);
        transition: 500ms;
      }
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
        transition: 300ms;

        &:hover {
          transform: scale(1.1);
          transition: 300ms;
        }
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

<script>
import FooterNewsItem from "./FooterNewsItem.vue";
import FooterBanner from "./FooterBanner.vue";

export default {
  name: "AppFooter",
  components: {
    FooterNewsItem,
    FooterBanner,
  },
  data() {
    return {
      lastYearGallery: [
        {
          name: "2 coffe",
          img: "photodune-7770665-two-white-coffee-mug-with-diy-decoration-o (1).jpg",
        },
        {
          name: "Speaker at business convenction",
          img: "photodune-8523683-speaker-at-business-convention-and-present.jpg",
        },
        {
          name: "Man realxing",
          img: "photodune-6745579-modern-creative-man-relaxing-on-workspace-.jpg",
        },
        {
          name: "Speaker at convention from behind",
          img: "photodune-8522811-speaker-at-business-conference-and-present (1).jpg",
        },
        {
          name: "Multiethnic people with satrup business",
          img: "photodune-8797753-multiethnic-people-with-startup-business-t (1).jpg",
        },
        {
          name: "Cards",
          img: "card04-150x150.jpg",
        },
        {
          name: "Wirstwatch, calendar, key, glasses",
          img: "photodune-6745606-man-wristwatch-calendar-key-and-glasses-on.jpg",
        },
        {
          name: "Creative Workspace",
          img: "photodune-6745585-modern-creative-workspace-m-150x150.jpg",
        },
        {
          name: "Girl listeng music",
          img: "6426608875_186070f8ca_o-150x150.jpg",
        },
        {
          name: "Card small",
          img: "card01-150x150.jpg",
        },
        {
          name: "Shore",
          img: "13349065283_64d09b067c_o-150x150.jpg",
        },
        {
          name: "Denim Clothes",
          img: "photodune-8795110-overhead-of-essentials-denim-clothes-m-150.jpg",
        },
      ],
      recentNews: [
        {
          title: "sem porta mollis parturient",
          link: "/newslink1",
        },
        {
          title: "nullam lorem matis purus",
          link: "/newslink2",
        },
        {
          title: "nibh sem sit ullamcorper",
          link: "/newslink3",
        },
        {
          title: "magna pars studiorum",
          link: "/newslink4",
        },
      ],
    };
  },
};
</script>

<template>
  <div class="container-fluid">
    <div class="container">
      <section>
        <h4>ABOUT US</h4>
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Alias rerum
          molestiae maiores nam tempora tempore.
        </p>
        <div class="socials">
          <i class="fa-brands fa-square-facebook"></i>
          <i class="fa-brands fa-square-twitter"></i>
          <i class="fa-brands fa-linkedin"></i>
          <i class="fa-brands fa-square-google-plus"></i>
          <i class="fa-brands fa-square-pinterest"></i>
          <i class="fa-brands fa-flickr"></i>
        </div>
      </section>
      <section>
        <h4>RECENT NEWS</h4>
        <ul>
          <FooterNewsItem
            v-for="(news, index) in recentNews"
            :key="index"
            :newsItem="news"
          ></FooterNewsItem>
        </ul>
      </section>
      <section>
        <h4>GET YOUR SEAT!</h4>
        <p>Book for your seat before it's too late.</p>
        <p>We provide a variety of ticket options</p>
        <button>CHECK OUT TICKETS!</button>
      </section>
      <section>
        <h4>GALLERY FROM LAST YEAR</h4>
        <div class="img-wrapper">
          <img
            v-for="(pic, index) in this.lastYearGallery"
            :key="index"
            :src="`../src/assets/images/${pic.img}`"
            :alt="pic.name"
          />
        </div>
      </section>
    </div>
  </div>
  <FooterBanner></FooterBanner>
</template>

<style lang="scss" scoped>
@use "../styles/partials/variables" as *;

.container-fluid {
  background-color: $mineShaft;
  .container {
    display: flex;
    flex-direction: row;
    gap: 0.5em;
    align-items: flex-start;
    padding: 2em 0;

    section {
      width: calc(100% / 4);
      display: flex;
      align-items: flex-start;
      flex-direction: column;
      & > * {
        margin-bottom: 1em;
      }
      h4 {
        color: $white;
        margin-bottom: 2em;
        font-weight: 400;
      }
      p {
        font-size: 0.9rem;
        font-weight: 300;
        color: $gray;
      }

      .socials {
        color: $white;
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
        gap: 1em;
        i {
          transition: 400ms;
        }

        i:hover {
          transform: scale(1.5);
          transition: 300ms;
        }
      }

      button {
        background-color: $scarlet;
        color: white;
        padding: 1em;
        border-bottom: 3px solid $thunderbird;
      }

      ul {
        color: $gray;
        text-transform: uppercase;
        font-size: 0.8rem;
        list-style-position: inside;
      }

      .img-wrapper {
        width: 100%;
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        gap: 0.5em;
        img {
          width: calc(100% / 4 - 0.5em);
          transition: 300ms;
          cursor: pointer;
          &:hover {
            transform: scale(1.2);
            transition: 300ms;
          }
        }
      }
    }
  }

  @media screen and (max-width: 800px) {
    .container {
      flex-wrap: wrap;
      section {
        width: 100%;
      }
    }
  }
}
</style>

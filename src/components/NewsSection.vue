<script>
export default {
  namae: "NewsSection",
  data() {
    return {
      news: [
        {
          img: "photodune-7770665-two-white-coffee-mug-with-diy-decoration-o.jpg",
          title: "Sedial eiusmod tempor",
          date: "03 Dec 2013",
          comments: 0,
          txt: " Lorem ipsum dolor sit amet consectetur adipisicing elit. Dignissimo ipsa quia maiores recusandae sunt vitae id dolorum cumque, quae quo minus excepturi velit ...",
          longTxt:
            "  Lorem ipsum dolor sit amet consectetur adipisicing elit. Veritatis odio eveniet pariatur, eius fuga obcaecati consequuntur qui repellendus cum consequatur nulla. Eum aliquid maxime hic deleniti? Consequatur optio expedita culpa mollitia minus itaque consequuntur saepe aliquid ut officiis, rem nam doloribus minima velit? Officia voluptas dolor modi corporis non, ea, animi doloribus vero nisi minus, sunt tenetur! Magni corporis adipisci aliquam nihil repudiandae iusto non cum omnis ea dicta voluptates voluptatibus nesciunt, laborum modi harum dolor voluptas qui, veritatis, voluptatum magnam ut? Magni eaque aliquid vero quam repudiandae ullam voluptates, quidem iure exercitationem laborum minima sunt, voluptate beatae neque tenetur voluptatem atque nisi vel? Aperiam odit nihil a labore ut veritatis eaque nobis adipisci cumque facilis sunt accusamus inventore placeat, quasi veniam unde atque voluptas, incidunt odio quisquam ab expedita obcaecati. Nesciunt harum cumque deserunt quasi quidem, laborum veritatis, magni architecto provident culpa laudantium consequatur suscipit, similique molestiae alias nobis.",
          link: "Read More",
          showMore: false,
        },
        {
          img: "photodune-8797753-multiethnic-people-with-startup-business-t.jpg",
          title: "donec luctus imperdiet",
          date: "03 Dec 2013",
          comments: 2,
          txt: " Lorem ipsum dolor sit amet consectetur adipisicing elit. Dignissimo ipsa quia maiores recusandae sunt vitae id dolorum cumque, quae quo minus excepturi velit ...",
          longTxt:
            "  Lorem ipsum dolor sit amet consectetur adipisicing elit. Veritatis odio eveniet pariatur, eius fuga obcaecati consequuntur qui repellendus cum consequatur nulla. Eum aliquid maxime hic deleniti? Consequatur optio expedita culpa mollitia minus itaque consequuntur saepe aliquid ut officiis, rem nam doloribus minima velit? Officia voluptas dolor modi corporis non, ea, animi doloribus vero nisi minus, sunt tenetur! Magni corporis adipisci aliquam nihil repudiandae iusto non cum omnis ea dicta voluptates voluptatibus nesciunt, laborum modi harum dolor voluptas qui, veritatis, voluptatum magnam ut? Magni eaque aliquid vero quam repudiandae ullam voluptates, quidem iure exercitationem laborum minima sunt, voluptate beatae neque tenetur voluptatem atque nisi vel? Aperiam odit nihil a labore ut veritatis eaque nobis adipisci cumque facilis sunt accusamus inventore placeat, quasi veniam unde atque voluptas, incidunt odio quisquam ab expedita obcaecati. Nesciunt harum cumque deserunt quasi quidem, laborum veritatis, magni architecto provident culpa laudantium consequatur suscipit, similique molestiae alias nobis.",
          link: "Read More",
          showMore: false,
        },
        {
          img: "photodune-8522811-speaker-at-business-conference-and-present.jpg",
          title: "Magna para studiorum",
          date: "03 Dec 2013",
          comments: 2,
          txt: " Lorem ipsum dolor sit amet consectetur adipisicing elit. Dignissimo ipsa quia maiores recusandae sunt vitae id dolorum cumque, quae quo minus excepturi velit ...",
          longTxt:
            "  Lorem ipsum dolor sit amet consectetur adipisicing elit. Veritatis odio eveniet pariatur, eius fuga obcaecati consequuntur qui repellendus cum consequatur nulla. Eum aliquid maxime hic deleniti? Consequatur optio expedita culpa mollitia minus itaque consequuntur saepe aliquid ut officiis, rem nam doloribus minima velit? Officia voluptas dolor modi corporis non, ea, animi doloribus vero nisi minus, sunt tenetur! Magni corporis adipisci aliquam nihil repudiandae iusto non cum omnis ea dicta voluptates voluptatibus nesciunt, laborum modi harum dolor voluptas qui, veritatis, voluptatum magnam ut? Magni eaque aliquid vero quam repudiandae ullam voluptates, quidem iure exercitationem laborum minima sunt, voluptate beatae neque tenetur voluptatem atque nisi vel? Aperiam odit nihil a labore ut veritatis eaque nobis adipisci cumque facilis sunt accusamus inventore placeat, quasi veniam unde atque voluptas, incidunt odio quisquam ab expedita obcaecati. Nesciunt harum cumque deserunt quasi quidem, laborum veritatis, magni architecto provident culpa laudantium consequatur suscipit, similique molestiae alias nobis.",
          link: "Read More",
          showMore: false,
        },
      ],
      readMore: false,
    };
  },
  methods: {
    showFullTxt(index) {
      this.news[index].showMore = !this.news[index].showMore;
    },
  },
};
</script>

<template>
  <div class="container">
    <div class="news-header">
      <h2>RECENT NEWS</h2>
      <a href="">Read All News</a>
    </div>
    <div class="news-articles">
      <div class="card" v-for="(newsArticle, index) in news" :key="index">
        <div class="card-img">
          <img
            :src="`../src/assets/images/${newsArticle.img}`"
            :alt="newsArticle.title"
          />
          <div class="sticky">
            <i class="fa-solid fa-bullhorn"></i> sticky post
          </div>
        </div>
        <div class="card-txt">
          <p class="date">
            {{ newsArticle.date }} / {{ newsArticle.comments }} Comments
          </p>
          <h4>{{ newsArticle.title }}</h4>
          <p v-show="newsArticle.showMore === false">
            {{ newsArticle.txt }}
          </p>
          <p class="long" v-show="newsArticle.showMore">
            {{ newsArticle.longTxt }}
          </p>

          <a
            v-show="!newsArticle.showMore"
            href=""
            @click.prevent="showFullTxt(index)"
            >{{ newsArticle.link }}</a
          >
          <a
            v-show="newsArticle.showMore"
            href=""
            @click.prevent="showFullTxt(index)"
            >Read less</a
          >
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "../styles/partials/variables" as *;

.container {
  padding: 4em 0 2em;
  z-index: 999;
}

.news-header {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  margin-bottom: 3em;
  a {
    color: $scarlet;
    font-weight: 300;
  }
}

.news-articles {
  display: flex;
  flex-direction: row;
  align-items: flex-start;
  gap: 1em;

  .card {
    width: calc(100% / 3);
    height: 350px;
    margin-bottom: 2em;
    // overflow: scroll;

    .card-img {
      position: relative;
      img {
        display: block;
      }
      .sticky {
        position: absolute;
        right: 0;
        bottom: 0;
        z-index: 999;
        color: white;
        background-color: $black;
        padding: 0.7em 1em;
        font-size: 0.6rem;
        text-transform: uppercase;
        display: none;
      }
    }

    .card-txt > * {
      margin-bottom: 1.3em;
    }

    .card-txt {
      height: 50%;
      h4 {
        text-transform: uppercase;
      }

      .date {
        letter-spacing: 0.1em;
        font-style: italic;
        margin-top: 1em;
      }
      p {
        font-weight: 300;
        color: $gray;
        font-size: 0.8rem;
      }
      .long {
        overflow: scroll;
        height: 150px;
      }

      a {
        color: $scarlet;
        font-weight: 300;
        font-style: italic;
      }
      &:hover {
        .sticky {
          display: block;
        }
      }
    }
  }
}
</style>

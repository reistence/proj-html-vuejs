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
          link: "Read More",
        },
        {
          img: "photodune-8797753-multiethnic-people-with-startup-business-t.jpg",
          title: "donec luctus imperdiet",
          date: "03 Dec 2013",
          comments: 2,
          txt: " Lorem ipsum dolor sit amet consectetur adipisicing elit. Dignissimo ipsa quia maiores recusandae sunt vitae id dolorum cumque, quae quo minus excepturi velit ...",
          link: "Read More",
        },
        {
          img: "photodune-8522811-speaker-at-business-conference-and-present.jpg",
          title: "Magna para studiorum",
          date: "03 Dec 2013",
          comments: 2,
          txt: " Lorem ipsum dolor sit amet consectetur adipisicing elit. Dignissimo ipsa quia maiores recusandae sunt vitae id dolorum cumque, quae quo minus excepturi velit ...",
          link: "Read More",
        },
      ],
    };
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
        <img :src="`../src/assets/images/${newsArticle.img}`" alt="" />
        <p class="date">
          {{ newsArticle.date }} / {{ newsArticle.comments }} Comments
        </p>
        <h4>{{ newsArticle.title }}</h4>
        <p>
          {{ newsArticle.txt }}
        </p>

        <a href="">{{ newsArticle.link }}</a>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "../styles/partials/variables" as *;

.container {
  padding: 3em 0;
  height: 500px;
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
    height: 300px;
    margin-bottom: 2em;

    & > * {
      margin-bottom: 1em;
    }
    h4 {
      text-transform: uppercase;
    }

    .date {
      letter-spacing: 0.1em;
    }
    p {
      font-weight: 300;
      color: $gray;
      font-size: 0.8rem;
    }

    a {
      color: $scarlet;
      font-weight: 300;
      font-style: italic;
    }
  }
}
</style>

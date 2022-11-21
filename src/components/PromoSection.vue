<script>
// import Vue from "vue";
// import Embed from "v-video-embed";

// global register
// Vue.use(Embed);
import { vueVimeoPlayer } from "vue-vimeo-player";

export default {
  name: "PromoSection",
  data() {
    return {
      videoId: "84467622",
      options: {
        responsive: true,
        autoplay: false,
        byline: false,
        dnt: true,
        title: false,
      },
    };
  },
  components: {
    vueVimeoPlayer,
  },
};
</script>
<template>
  <div class="container">
    <div class="presentation">
      <h2>presentation</h2>
      <div class="vidWrapper">
        <vueVimeoPlayer
          :video-id="videoId"
          :options="options"
          ref="player"
        ></vueVimeoPlayer>
      </div>
      <!-- <img src="../assets/images/461365506_640.jpg" alt="Last Conference" /> -->
    </div>
    <div class="twitter-feeds">
      <h2>twitter feeds</h2>
      <ul>
        <li>
          <i class="fa-brands fa-twitter"></i>
          <div class="feed-txt">
            <p>
              Stand out an be vibrant with some of the best bright and bold
              templates on <span>@Envato</span> Elements. And add a splash of
              c...
              <span>https://t.co/jFrsnzEJK7</span>
            </p>
            <p>3 days ago</p>
          </div>
        </li>
        <li>
          <i class="fa-brands fa-twitter"></i>
          <div class="feed-txt">
            <p>
              Do you need to deliver the perfect presentation or creative pitch?
              Sure, your ideas and plans need to be on-point, b...
              <span>https://t.co/nCmvcJVDpW</span>
            </p>
            <p>9 days ago</p>
          </div>
        </li>
        <li>
          <i class="fa-brands fa-twitter"></i>
          <div class="feed-txt">
            <p>
              Cut yourself a piece of the BFCM sales pie with a solid marketing
              plan. Here are 5 ways to optimize your content fo...
              <span>https://t.co/UZfKHshE0T</span>
            </p>
            <p>11 days ago</p>
          </div>
        </li>
      </ul>
    </div>
  </div>
</template>
<style lang="scss" scoped>
@use "../styles/partials/variables" as *;

.container {
  display: flex;
  flex-direction: row;
  padding: 2em 0;
  gap: 5em;
}

.presentation {
  width: 40%;
  h2 {
    text-transform: uppercase;
    margin-bottom: 2em;
  }

  .vidWrapper {
    margin-left: 2em;
  }
}

.twitter-feeds {
  width: 50%;
  h2 {
    text-transform: uppercase;
    margin-bottom: 2em;
  }

  li {
    display: flex;
    flex-direction: row;
    align-items: flex-start;
    justify-content: space-between;
    gap: 1em;
    margin-bottom: 1em;

    i {
      color: rgb(90, 190, 252);
    }

    p:last-child {
      font-size: 0.8rem;
      margin: 1em 0;
    }
  }

  p {
    color: $gray;
    font-weight: 200;
    font-style: italic;
    font-size: 0.9rem;
  }

  span {
    color: $scarlet;
  }
}
</style>

<script>
export default {
  name: "BannerCountDown",
  data() {
    return {
      days: null,
      hours: null,
      minutes: null,
      seconds: null,
    };
  },
  created() {
    setInterval(this.updateCount, 1000);
  },
  computed: {},
  methods: {
    updateCount() {
      const thisYear = new Date().getFullYear();
      const target = new Date(`January 01 ${thisYear + 11} 00:00:00`);

      const today = new Date();
      const diff = target - today;
      this.days = Math.floor(diff / 1000 / 60 / 60 / 24);
      this.hours = Math.floor(diff / 1000 / 60 / 60) % 24;
      this.minutes = Math.floor(diff / 1000 / 60) % 60;
      this.seconds = Math.floor(diff / 1000) % 60;
    },
  },
};
</script>

<template>
  <div class="container-fluid">
    <div class="wrapper">
      <div class="countdown">
        <div class="days">
          <p v-text="this.days"></p>
          <p>days</p>
        </div>
        <div>
          <p v-text="this.hours < 10 ? '0' + this.hours : this.hours"></p>
          <p>hours</p>
        </div>
        <div>
          <p v-text="this.minutes < 10 ? '0' + this.minutes : this.minutes"></p>
          <p>mins</p>
        </div>
        <div id="secs">
          <p
            id="secsN"
            v-text="this.seconds < 10 ? '0' + this.seconds : this.seconds"
          ></p>
          <p id="secsP">secs</p>
        </div>
      </div>
      <div class="banner-txt">
        <p>subscribe for updates</p>
        <div>
          <input type="email" placeholder="Please fill your email" />
          <button @click="updateCount">Subscribe</button>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "../styles/partials/variables" as *;

.container-fluid {
  height: 500px;
  background-image: url(../assets/images/coutdown-bg1.jpg);
  background-position: center;
  background-size: cover;
  background-repeat: repeat-x;
  position: relative;

  .wrapper {
    position: absolute;
    width: 50%;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);

    .countdown {
      display: flex;
      flex-direction: row;
      justify-content: center;
      align-items: stretch;

      gap: 1em;

      div {
        background-color: rgba(0, 0, 0, 0.77);
        padding: 1.5em;
        width: max-content;
        margin-bottom: 1em;
        border-radius: 5px;
        color: $white;
        text-align: center;
        position: relative;

        p:first-child {
          font-size: 4rem;
          transition: all 300ms linear;
        }
        p:nth-child(2) {
          text-transform: uppercase;
          font-size: 1rem;
        }

        // #secs {
        //   width: 10em;
        // }

        // #secsN {
        //   position: absolute !important;
        //   top: 45%;
        //   left: 50%;
        //   transform: translate(-50%, -50%);
        // }
        // #secsP {
        //   position: absolute;
        //   bottom: 15%;
        //   left: 50%;
        //   transform: translate(-50%, -50%);
        // }
      }
    }

    .banner-txt {
      p {
        text-transform: uppercase;
        font-size: 1.4rem;
        text-align: center;
        margin-bottom: 1em;
        font-weight: 500;
      }
      div {
        width: 100%;
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: center;
        gap: 1em;

        input {
          width: 50%;
          height: 40px;
          padding: 0.2em 0.5em;
          font-size: 1rem;
          appearance: none;
          border: none;
        }

        button {
          background-color: $scarlet;
          color: white;
          font-size: 0.8rem;
          font-weight: bold;
          text-transform: uppercase;
          padding: 1em 1em;
        }
      }
    }
  }
}
</style>

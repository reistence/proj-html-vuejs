<script>
export default {
  name: "BannerCountDown",
  data() {
    return {
      days: "",
      hours: "",
      minutes: "",
      seconds: "",
    };
  },
  created() {
    //start countdown when page is created
    this.updateCount();
    setInterval(this.updateCount, 1000);
  },
  methods: {
    updateCount() {
      // set current year, current day and  the target countdown date
      const thisYear = new Date().getFullYear();
      const target = new Date(`January 01 ${thisYear + 11} 00:00:00`);
      const today = new Date();
      // calculate the difference and uptade data accordingly
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
  height: 450px;
  background-image: url(../assets/images/coutdown-bg1.jpg);
  background-position: center;
  background-size: auto;
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
      width: 100%;

      div {
        background-color: rgba(0, 0, 0, 0.671);
        padding: 1.5em 1.5em;
        width: max-content;

        width: calc(100% / 3);
        border-radius: 5px;
        color: $white;
        position: relative;
        display: flex;
        flex-direction: column;
        align-items: center;

        p:first-child {
          font-size: 3.5rem;
          transition: all 300ms linear;
          text-align: center;
        }
        p:nth-child(2) {
          text-transform: uppercase;
          font-size: 1rem;
          font-weight: 300;
          text-align: center;
        }
      }

      div:first-child {
        background-color: rgba(0, 0, 0, 0.963);
      }
      div:nth-child(2) {
        background-color: rgba(0, 0, 0, 0.671);
      }
      div:nth-child(3) {
        background-color: rgba(0, 0, 0, 0.532);
      }
      div:last-child {
        background-color: rgba(0, 0, 0, 0.425);
      }
    }

    .banner-txt {
      margin-top: 2em;
      p {
        text-transform: uppercase;
        font-size: 1.4rem;
        text-align: center;
        margin-bottom: 1em;
        font-weight: 600;
      }
      div {
        width: 100%;
        height: 50px;
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: center;
        gap: 1em;

        input {
          width: 50%;
          height: 100%;
          padding: 0.2em 1em;
          font-size: 0.8rem;
          appearance: none;
          border: none;
        }
        ::placeholder {
          color: rgb(207, 200, 200);
          font-weight: 100;
        }

        button {
          background-color: $scarlet;
          color: white;
          height: 100%;
          font-size: 0.9rem;
          font-weight: bold;
          text-transform: uppercase;
          padding: 1em 1.5em;
          border-bottom: 3px solid $thunderbird;
        }
      }
    }
  }
}

@media screen and (max-width: 800px) {
  .container-fluid {
    .wrapper {
      .countdown {
        flex-wrap: wrap;
        div {
          padding: 1em;
          p:first-child {
            font-size: 2rem;
          }
        }
      }

      .banner-txt {
        p {
          font-size: 1rem;
          margin-bottom: 1.5em;
        }
        div {
          flex-direction: column;
          input {
            width: 100%;
          }
          button {
            font-size: 0.7rem;
            padding: 0.5em;
          }
        }
      }
    }
  }
}
@media screen and (max-width: 450px) {
  .container-fluid {
    .wrapper {
      .countdown {
        flex-wrap: wrap;
        div {
          padding: 1em;
          p:first-child {
            font-size: 1rem;
          }
          p:nth-child(2) {
            text-transform: lowercase;
          }
        }
      }
    }
  }
}
</style>

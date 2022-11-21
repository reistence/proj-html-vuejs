<script>
export default {
  name: "SpeakersSlider",
  data() {
    return {
      speakers: [
        {
          name: "Patrick Spencer",
          role: "S&P Analyser",
          img: "-6",
          active: true,
        },
        {
          name: "Janet Jones",
          role: "Newyork Posts's GM",
          img: "-5",
          active: true,
        },
        {
          name: "Micheal Dover",
          role: "Starbuck's CEO",
          img: "-4",
          active: true,
        },
        {
          name: "Angelina Holy",
          role: "Maxii's Manager",
          img: "-3",
          active: true,
        },
        {
          name: "Laurence Francis",
          role: "Bho CFO",
          img: "-1",
          active: false,
        },
        {
          name: "john Doe",
          role: "Market Manager",
          img: "-2",
          active: false,
        },
        {
          name: "Bob Barkley",
          role: "Bho Sales Manager",
          img: "-7",
          active: false,
        },
        {
          name: "Sara O'Neil",
          role: "No Idea CTO",
          img: "-8",
          active: false,
        },
      ],
      counter: 0,
    };
  },
  methods: {
    showNext4() {
      let firstFour;
      let secondFour;
      firstFour = this.speakers.slice(0, 4);
      secondFour = this.speakers.slice(4, 8);

      if (this.counter === 0) {
        secondFour.forEach((element) => {
          element.active = true;
        });
        firstFour.forEach((element) => {
          element.active = false;
        });
        this.counter++;
      } else {
        firstFour.forEach((element) => {
          element.active = true;
        });
        secondFour.forEach((element) => {
          element.active = false;
        });
        this.counter--;
      }
    },
    showPrev4() {
      let firstFour;
      let secondFour;
      firstFour = this.speakers.slice(0, 4);
      secondFour = this.speakers.slice(4, 8);
      if (this.counter === 0) {
        secondFour.forEach((element) => {
          element.active = true;
        });
        firstFour.forEach((element) => {
          element.active = false;
        });
        this.counter++;
      } else {
        firstFour.forEach((element) => {
          element.active = true;
        });
        secondFour.forEach((element) => {
          element.active = false;
        });
        this.counter--;
      }
    },
  },
};
</script>

<template>
  <div class="wrapper">
    <div class="container">
      <div class="slider-header">
        <h2>speakers</h2>
        <div class="btns">
          <button @click="showPrev4">
            <i class="fa-solid fa-chevron-left"></i>
          </button>
          <button @click="showNext4">
            <i class="fa-solid fa-chevron-right"></i>
          </button>
        </div>
      </div>
      <div class="slider-content">
        <div
          class="speaker-card"
          v-for="(speaker, index) in speakers"
          v-show="speaker.active"
          :key="index"
        >
          <div class="card-img">
            <img
              :src="`../src/assets/images/speaker${speaker.img}.jpg`"
              :alt="speaker.name"
              srcset=""
            />
            <div class="layer">
              <div>
                <i class="fa-brands fa-twitter"></i>
                <i class="fa-brands fa-facebook-f"></i>
                <i class="fa-brands fa-linkedin"></i>
              </div>
            </div>
          </div>
          <h4>{{ speaker.name }}</h4>
          <p>{{ speaker.role }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "../styles/partials/variables" as *;

.wrapper {
  background-color: $greybg;
}
.container {
  display: flex;
  flex-direction: column;
  padding: 2em 0;

  .slider-header {
    display: flex;
    padding: 2em 0;
    margin-bottom: 1em;
    flex-direction: row;
    flex-wrap: nowrap;
    justify-content: space-between;
    align-items: center;
    h2 {
      text-transform: uppercase;
      font-size: 2rem;
    }
    .btns {
      display: flex;
      flex-direction: row;
      gap: 1em;
      button {
        background-color: $scarlet;
        color: $white;
        padding: 1em;
        border-radius: 5px;
      }
    }
  }

  .slider-content {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 2em;
    overflow-y: hidden;

    .speaker-card {
      width: calc(100% / 4 - 1em);
      text-align: center;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      transition: 900ms;

      .card-img {
        border-radius: 5px;
        position: relative;
        transition: 900ms;
        img {
          display: block;
        }
        &:hover {
          .layer {
            display: flex;
            transition: 900ms;
          }
        }
      }

      .layer {
        background-color: #bf341f8c;
        position: absolute;
        transition: 900ms;
        width: 100%;
        top: 0%;
        left: 0;
        height: 100%;
        color: $white;
        display: none;
        justify-content: center;
        align-items: center;
        div {
          & > * {
            margin-right: 0.5em;
            cursor: pointer;
          }
        }
      }
      h4 {
        text-transform: uppercase;
        margin-top: 1em;
        font-weight: 400;
        margin-bottom: 0.5em;
      }
      p {
        font-weight: 200;
        font-size: 0.8rem;
        font-style: italic;
      }
    }
  }
}
</style>

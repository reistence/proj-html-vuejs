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
          name: "Bho",
          role: "Bho CFO",
          img: "-1",
          active: false,
        },
        {
          name: "Foo",
          role: "Market Manager",
          img: "-2",
          active: false,
        },
        {
          name: "Fuzz",
          role: "Bho Sales Manager",
          img: "-7",
          active: false,
        },
        {
          name: "Bar",
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
  <div>
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
          <img
            :src="`../src/assets/images/speaker${speaker.img}.jpg`"
            :alt="speaker.name"
            srcset=""
          />
          <h4>{{ speaker.name }}</h4>
          <p>{{ speaker.role }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "../styles/partials/variables" as *;

div {
  background-color: $greybg;
}
.container {
  display: flex;
  flex-direction: column;
  padding: 1em 0;

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
      img {
        border-radius: 5px;
      }
      h4 {
        text-transform: uppercase;
        margin-top: 1em;
        font-weight: 400;
        margin-bottom: 1em;
      }
      p {
        font-weight: 200;
      }
    }
  }
}
</style>

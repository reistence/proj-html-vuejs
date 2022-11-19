<script>
export default {
  name: "EventsJournal",
  data() {
    return {
      events: [
        {
          name: "day 1",
          date: "25 May 2030",
          active: false,
        },
        {
          name: "day 2",
          date: "23 May 2030",
          active: false,
        },
        {
          name: "day 3",
          date: "24 May 2030",
          active: false,
        },
        {
          name: "day 4",
          date: "25 May 2030",
          active: false,
        },
        {
          name: "day 5",
          date: "26 May 2030",
          active: false,
        },
      ],
      eventDetails: [
        {
          time: "09:00 - 10:30",
          room: "ROOM A",
          speaker: "Laurence Francis",
          topic: "welcome and introduction",
          desciption:
            "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quidem sequi, excepturi animi recusandae sint soluta?Lorem ipsum dolor sit amet consectetur adipisicing elit",
          speakerImg: "-1",
          active: true,
        },
        {
          time: "10:00 - 11:30",
          room: "ROOM C",
          speaker: "John Doe",
          topic: "Business Plans 101",
          desciption:
            "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quidem sequi, excepturi animi recusandae sint soluta?Lorem ipsum dolor sit amet consectetur adipisicing elit",
          speakerImg: "-2",
          active: false,
        },
        {
          time: "11:00 - 12:30",
          room: "ROOM 302",
          speaker: "Bob Barkley",
          topic: "Web 2.0",
          desciption:
            "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quidem sequi, excepturi animi recusandae sint soluta?Lorem ipsum dolor sit amet consectetur adipisicing elit",
          speakerImg: "-7",
          active: false,
        },
        {
          time: "09:30 - 11:30",
          room: "ROOM B",
          speaker: "Sara O'neil",
          topic: "IoT",
          desciption:
            "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quidem sequi, excepturi animi recusandae sint soluta?Lorem ipsum dolor sit amet consectetur adipisicing elit",
          speakerImg: "-8",
          active: false,
        },
        {
          time: "09:00 - 12:00",
          room: "ROOM A",
          speaker: "Angelina Holy",
          topic: "Final Project and salutation",
          desciption:
            "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quidem sequi, excepturi animi recusandae sint soluta?Lorem ipsum dolor sit amet consectetur adipisicing elit",
          speakerImg: "-3",
          active: false,
        },
      ],
      currentEvent: 0,
    };
  },
  methods: {
    showEvent(clickedEvent) {
      this.currentEvent = clickedEvent;
    },
  },
};
</script>
<template>
  <div class="container">
    <div class="events-header">
      <h2>program</h2>
      <p>
        This conference run through all 4 days from 23-26 May 2016. <br />
        We also provide free lunch and coffee break in each day.
      </p>

      <a href="">View Full Program</a>
    </div>
    <div class="program-schedule">
      <div class="program-header">
        <div
          class="day"
          v-for="(event, index) in events"
          :key="index"
          @click="showEvent(index)"
          :class="currentEvent === index ? 'active' : ''"
        >
          <h3>{{ event.name }}</h3>
          <p>{{ event.date }}</p>
        </div>
      </div>
      <div
        class="program"
        v-for="(program, index) in eventDetails"
        :key="index"
        v-show="
          currentEvent === index
            ? (program.active = true)
            : (program.active = false)
        "
      >
        <div class="program-info">
          <div>
            <i class="fa-regular fa-clock"></i>
            <p>{{ program.time }}</p>
          </div>
          <div>
            <i class="fa-solid fa-location-arrow"></i>
            <p>{{ program.room }}</p>
          </div>
          <div>
            <i class="fa-solid fa-user"></i>
            <p id="speaker">{{ program.speaker }}</p>
          </div>
        </div>
        <div class="program-content">
          <h3>{{ program.topic }}</h3>
          <p>
            {{ program.desciption }}
          </p>
          <img
            :src="`../src/assets/images/speaker${program.speakerImg}.jpg`"
            :alt="program.speaker"
          />
        </div>
      </div>
    </div>
  </div>
</template>
<style lang="scss">
@use "../styles/partials/variables" as *;

.container {
  padding: 3em 0;
}

.events-header {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
  padding: 1em 0;
  margin: 1em 0;
  h2 {
    text-transform: uppercase;
  }
  p {
    width: 60%;
    font-weight: 200;
    color: $gray;
    font-size: 0.9rem;
  }
  a {
    color: $scarlet;
    font-weight: 200;
    font-style: italic;
  }
}

.program-header {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: flex-start;
  background-color: $scarlet;
  .day {
    color: white;
    width: calc(100% / 6);
    padding: 0.8em 1em;
    border-right: 1px solid $thunderbird;
    cursor: pointer;
    h3 {
      text-transform: uppercase;
      margin-bottom: 0.3em;
      font-size: 1rem;
    }
    p {
      font-weight: 300;
      font-size: 0.9rem;
    }

    &.active {
      background-color: $thunderbird;
    }
  }
}

.program {
  display: flex;
  flex-direction: row;
  align-items: flex-start;
  justify-content: flex-start;
  padding: 2.5em 1em;
  background-color: #f3f3f3;
  height: 250px;

  &-info {
    width: 25%;
    font-size: 0.7rem;

    div {
      margin-bottom: 1em;
      display: flex;
      flex-direction: row;
      justify-content: flex-start;
      gap: 1em;
      align-items: baseline;
      width: 80%;
      margin: 1em auto;

      p {
        font-size: 0.7rem;
        font-weight: 200;
        color: $gray;
      }
    }
  }

  &-content {
    width: 65%;

    h3 {
      font-weight: 400;
      margin: 0.5em 0 1em 0;
      text-transform: uppercase;
    }
    p {
      font-size: 0.9rem;
      font-weight: 200;
      margin-bottom: 1em;
      color: $gray;
    }
    img {
      width: 3em;
      height: 3em;
      object-fit: cover;
      border-radius: 5px;
    }
  }
  #speaker {
    text-transform: uppercase;
    font-weight: 300;
    color: $scarlet;
  }
}
</style>

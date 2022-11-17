<script>
export default {
  name: "EventsJournal",
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
        <div class="day">
          <h3>DAY 1</h3>
          <p>23 May 2023</p>
        </div>
        <div class="day">
          <h3>DAY 2</h3>
          <p>23 May 2030</p>
        </div>
        <div class="day">
          <h3>DAY 3</h3>
          <p>24 May 2030</p>
        </div>
        <div class="day">
          <h3>DAY 4</h3>
          <p>25 May 2030</p>
        </div>
        <div class="day">
          <h3>DAY 5</h3>
          <p>26 May 2030</p>
        </div>
      </div>
      <div class="program">
        <div class="program-info">
          <div>
            <i class="fa-regular fa-clock"></i>
            <p>09:00 - 10:30</p>
          </div>
          <div>
            <i class="fa-solid fa-location-arrow"></i>
            <p>ROOM A</p>
          </div>
          <div>
            <i class="fa-solid fa-user"></i>
            <p>LAURENCE FRANCIS</p>
          </div>
        </div>
        <div class="program-content">
          <h3>WELCOME AND INTRODUCTION</h3>
          <p>
            Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quidem
            sequi, excepturi animi recusandae sint soluta?Lorem ipsum dolor sit
            amet consectetur adipisicing elit.
          </p>
          <img src="../assets/images/speaker-1-150x150.jpg" alt="" />
        </div>
      </div>
    </div>
  </div>
</template>
<style lang="scss">
@use "../styles/partials/variables" as *;

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
    padding: 1em;
    border-right: 1px solid $thunderbird;
    p {
      font-weight: 200;
    }
  }
}

.program {
  display: flex;
  flex-direction: row;
  align-items: flex-start;
  justify-content: flex-start;
  padding: 1em;
  background-color: #f3f3f3;

  &-info {
    padding: 0em;
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
    }
  }

  &-content {
    width: 65%;
    padding: 0;

    h3 {
      font-weight: 400;
      margin: 0.5em 0 1em 0;
    }
    p {
      font-size: 0.9rem;
      font-weight: 200;
      margin-bottom: 1em;
      color: $gray;
    }
    img {
      width: 3em;
    }
  }
}
</style>

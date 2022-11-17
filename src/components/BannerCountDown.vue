<script>
export default {
  name: "BannerCountDown",
};
</script>

<template>
  <div class="container-fluid">
    <div class="wrapper">
      <div class="countdown">
        <div class="days">
          <p>3399</p>
          <p>days</p>
        </div>
        <div class="hours">
          <p>17</p>
          <p>hours</p>
        </div>
        <div class="mins">
          <p>28</p>
          <p>mins</p>
        </div>
        <div class="secs">
          <p>17</p>
          <p>secs</p>
        </div>
      </div>
      <div class="banner-txt">
        <p>subscribe for updates</p>
        <div>
          <input type="text" placeholder="Please fill your email" />
          <button>Subscribe</button>
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
      align-items: center;
      gap: 1em;

      div {
        background-color: rgba(0, 0, 0, 0.77);
        padding: 1.5em;
        margin-bottom: 1em;
        border-radius: 5px;
        color: $white;
        text-align: center;

        p:first-child {
          font-size: 4rem;
        }
        p:nth-child(2) {
          text-transform: uppercase;
          font-size: 1rem;
        }
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

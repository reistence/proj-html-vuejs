<script>
export default {
  name: "Jumbotron",
};
</script>
<template>
  <div class="container-fluid">
    <div class="jumbo-txt">
      <p>CONFERENCE ON</p>
      <h1>SOCIAL NETWORKS</h1>
      <img src="../assets/images/1-item-2.jpg" alt="" />
      <ul>
        <li>23 - 26 may 2019</li>
        /
        <li>san francisco</li>
        /
        <li>8 speakers</li>
      </ul>
      <button>register online</button>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "../styles/partials/variables" as *;

.container-fluid {
  height: 500px;
  position: relative;
  background-image: url(../assets/images/slider-1-bg.jpg);
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  .jumbo-txt {
    position: absolute;
    width: 60%;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    text-align: center;
    text-transform: uppercase;
    color: $white;

    p {
      font-size: 3rem;
      font-weight: 200;
      margin-bottom: 0.2em;
    }
    h1 {
      font-size: 4rem;
      margin-bottom: 0.3em;
    }
    ul {
      display: flex;
      flex-direction: row;
      flex-wrap: nowrap;
      align-items: center;
      justify-content: center;
      gap: 1.5em;
      margin: 1em 0;
      margin-bottom: 1.5em;
    }
    button {
      padding: 1em 1.5em;
      text-transform: uppercase;
      background-color: $scarlet;
      color: $white;
      border-radius: 5px;
      font-size: 1rem;
    }
  }
}
</style>

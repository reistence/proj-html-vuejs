<script>
export default {
  name: "AboutUs",
};
</script>
<template>
  <div class="container">
    <section>
      <i class="fa-solid fa-trophy"></i>
      <div class="txt">
        <h3>who we are</h3>
        <p>
          Donec id elit non mi porta gravida at eget me tus. Sed posuere
          consectetur estat lobo rtis. Cum sociis natoque.
        </p>
        <a href="">Learn more</a>
      </div>
    </section>
    <section>
      <i class="fa-solid fa-bolt-lightning"></i>
      <div class="txt">
        <h3>What we do</h3>
        <p>
          Donec id elit non mi porta gravida at eget me tus. Sed posuere
          consectetur estat lobo rtis. Cum sociis natoque.
        </p>
        <a href="">Learn more</a>
      </div>
    </section>
    <section>
      <i class="fa-solid fa-question"></i>
      <div class="txt">
        <h3>why</h3>
        <p>
          Donec id elit non mi porta gravida at eget me tus. Sed posuere
          consectetur estat lobo rtis. Cum sociis natoque.
        </p>
        <a href="">Learn more</a>
      </div>
    </section>
  </div>
</template>

<style lang="scss" scoped>
@use "../styles/partials/variables" as *;

.container {
  display: flex;
  padding: 3em 0;
  flex-direction: row;
  justify-content: space-around;
  align-items: center;
  section {
    width: 27%;
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    align-items: flex-start;
    gap: 1.5em;
    i {
      color: $dustGrey;
      font-size: 1.5rem;
    }
    .txt {
      display: flex;
      flex-direction: column;
      justify-content: flex-start;
      align-items: flex-start;
      gap: 1em;
      h3 {
        text-transform: uppercase;
        color: $black;
      }
      p {
        color: $gray;
        font-weight: 100;
      }
      a {
        color: $scarlet;
        font-style: italic;
        font-weight: 100;
      }
    }
  }
}
</style>

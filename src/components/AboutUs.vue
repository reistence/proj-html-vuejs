<script>
export default {
  name: "AboutUs",
  data() {
    return {};
  },
};
</script>
<template>
  <div class="container">
    <div class="section-row">
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
  .section-row {
    width: 100%;
    display: flex;
    flex-direction: row;
    gap: 2em;
    padding: 1em 0;
    justify-content: center;
  }

  section {
    width: calc(100% / 3);
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
      margin-top: 0.3em;
      flex-direction: column;
      justify-content: flex-start;
      align-items: flex-start;
      gap: 1.5em;
      h3 {
        text-transform: uppercase;
        color: $black;
        font-weight: 500;
        font-size: 1.2rem;
      }
      p {
        color: $gray;
        font-weight: 200;
        font-size: 0.9rem;
      }
      a {
        color: $scarlet;
        font-style: italic;
        font-weight: 300;
      }
    }
  }
}
</style>

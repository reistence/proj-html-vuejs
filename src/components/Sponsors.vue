<script>
export default {
  name: "Sponsors",
  data() {
    return {
      sponsors: [
        {
          name: "Drogler",
          img: "1",
        },
        {
          name: "Link Sys",
          img: "2",
        },
        {
          name: "Pointer Co",
          img: "3",
        },
        {
          name: "Max Star",
          img: "4",
        },
        {
          name: "Globe Care",
          img: "5",
        },
        {
          name: "The Shield",
          img: "6",
        },
      ],
    };
  },
};
</script>

<template>
  <div class="container-fluid">
    <div class="container">
      <h2>SPONSORS</h2>
      <p>
        Maecenas faucibus mollis interdum. Nullam id dolor id nibh ultricies
        vehicula ut id elit.
      </p>
      <div class="sponsors-row">
        <div class="sponsor" v-for="(sponsor, index) in sponsors" :key="index">
          <img
            :src="`../src/assets/images/banner-${sponsor.img}.jpg`"
            :alt="sponsor.name"
          />
        </div>
      </div>
    </div>
  </div>
</template>
<style lang="scss" scoped>
@use "../styles/partials/variables" as *;

.container-fluid {
  background-color: $greybg;
}

.container {
  text-align: center;
  padding: 4em 0;
}
h2 {
  font-size: 2rem;
}
p {
  font-weight: 300;
  color: $gray;
  margin: 2em auto;
  width: 40%;
  font-size: 0.9rem;
}

.sponsors-row {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
  gap: 1.5em;
}

.sponsor {
  background-color: $white;
  transition: 300ms;
  cursor: pointer;
  width: calc(100% / 6);

  &:hover {
    transform: scale(1.2);
    transition: 300ms;
  }
}

@media screen and (max-width: 800px) {
  .sponsors-row {
    flex-wrap: wrap;
    width: 80%;
    margin: 0 auto;

    .sponsor {
      width: calc(100% / 4);
    }
  }
}
</style>

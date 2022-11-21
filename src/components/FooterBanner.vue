<script>
export default {
  name: "FooterBanner",
};
</script>
<template>
  <div class="container-fluid">
    <div class="container">
      <div>
        <p>Copyright Goodlayers, All Rights Reserved</p>
      </div>
      <div>
        <ul>
          <li>About us</li>
          <li>Accomodation</li>
          <li>Call for Paper</li>
          <li>Contact Us</li>
        </ul>
      </div>
    </div>
  </div>
</template>
<style lang="scss" scoped>
@use "../styles/partials/variables" as *;
.container-fluid {
  background-color: black !important;
}

.container {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
  color: $gray;
  font-size: 0.8rem;
}

ul {
  display: flex;
  flex-direction: row;
  gap: 1em;
}
li {
  position: relative;
}

li:not(:last-child)::after {
  content: "|";
  position: absolute;
  top: 0;
  right: -9px;
}

@media screen and (max-width: 800px) {
  .container {
    flex-wrap: wrap;
    gap: 1em;
  }

  ul {
    flex-direction: row;
    flex-wrap: wrap;
  }
}
</style>

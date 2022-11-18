<script>
export default {
  name: "LocationBanner",
};
</script>

<template>
  <div class="container-fluid">
    <div class="banner-txt">
      <h2>LOCATITON</h2>
      <h3>GD BUILDING, GRAND CONFERENCE ROOM</h3>
      <p>
        <i class="fa-solid fa-location-arrow"></i> 11 GD Building, River Mall,
        New York, USA 8879
      </p>
      <p><a href="">Check For Accomodations Here</a></p>
      <img src="../assets/images/1-item-2.jpg" alt="" />
      <div class="contacts">
        <div>
          <i class="fa-solid fa-phone"></i>
          <p>+1-112-222-3344</p>
        </div>
        <div>
          <i class="fa-solid fa-envelope"></i>
          <p>Contact@TheKeyniteTheme.com</p>
        </div>
      </div>
    </div>
  </div>
</template>
<style lang="scss" scoped>
@use "../styles/partials/variables" as *;

.container-fluid {
  background-image: url("../assets/images/location-bg.jpg");
  background-size: cover;
  background-position: center;
  height: 400px;
  position: relative;
}

.banner-txt {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 60%;
  transform: translate(-50%, -50%);
  color: $white;
  text-align: center;

  & > * {
    margin-bottom: 0.5em;
  }
  h2 {
    font-size: 2.5rem;
    margin-bottom: 0.5em;
  }
  h3 {
    font-size: 1.7rem;
    width: 100%;
  }
  a {
    color: $scarlet;
    font-size: 1.3rem;
    font-weight: 300;
  }
  p {
    font-weight: 300;
  }
}

.contacts {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  margin-top: 1em;
  gap: 1em;
  div {
    display: flex;
    flex-direction: row;
    align-items: center;
    gap: 0.5em;
    justify-content: center;
    font-weight: 300;
  }
}
</style>

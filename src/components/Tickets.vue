<script>
export default {
  name: "Tickets",
  data() {
    return {
      tickets: [
        {
          pass: "one day pass",
          cost: "FREE",
          benefits: [
            "One Day Access",
            "Coffee Break",
            "Lunch(International Buffet)",
            "Document Sheet",
            "50USD Voucher for next event",
          ],
        },
        {
          pass: "four days pass",
          cost: "750.00 USD",
          benefits: [
            "Four Days Access",
            "Coffee Break",
            "Lunch(International Buffet)",
            "Document Sheet",
            "100USD Voucher for next event",
          ],
        },
        {
          pass: "two days pass",
          cost: "580.00 USD",
          benefits: [
            "Two Days Access",
            "Coffee Break",
            "Lunch(International Buffet)",
            "Document Sheet",
            "70USD Voucher for next event",
          ],
        },
      ],
    };
  },
};
</script>

<template>
  <div class="container-fluid">
    <div class="container">
      <h1>TICKETS</h1>
      <div class="tickets-row">
        <div class="ticket" v-for="(ticket, index) in tickets" :key="index">
          <div class="offer">
            <h4>{{ ticket.pass }}</h4>
            <p>{{ ticket.cost }}</p>
            <h3 v-show="index === 1" class="ribbon">Featured!</h3>
          </div>
          <div class="details">
            <ul>
              <li v-for="(item, index) in ticket.benefits" :key="index">
                {{ item }}
              </li>
            </ul>
          </div>
          <button>BOOK NOW</button>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "../styles/partials/variables" as *;

.container-fluid {
  height: 500px;
  background-image: url(../assets/images/ticket-bg.jpg);
  background-size: cover;
  background-position: center;
  background-repeat: repeat-x;
  position: relative;
}

.container {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  h1 {
    text-align: center;
    color: $white;
    margin-bottom: 2em;
  }
}

.tickets-row {
  display: flex;
  flex-direction: row;
  align-items: flex-start;
  gap: 1.5em;
  width: 90%;
  margin: 2em auto;
}

.ticket {
  width: calc(100% / 3);
  text-align: center;
  transition: 500ms;

  &:hover {
    transform: scale(1.01) translateY(-5px);
  }
  .offer {
    background-color: $greybg;
    padding: 1em;
    border: none;
    overflow: hidden;
    position: relative;

    .ribbon {
      margin: 0;
      padding: 0;
      background: $scarlet;
      font-size: 0.7rem;
      font-weight: 500;
      color: white;
      padding: 0.5em 0;
      position: absolute;
      top: 0;
      right: 0;
      transform: translateX(30%) translateY(0%) rotate(45deg);
      transform-origin: top left;
    }
    .ribbon:before,
    .ribbon:after {
      content: "";
      position: absolute;
      top: 0;
      margin: 0 -1px; /* tweak */
      width: 100%;
      height: 100%;
      background: $scarlet;
    }
    .ribbon:before {
      right: 100%;
    }

    .ribbon:after {
      left: 100%;
    }
    h4 {
      text-transform: uppercase;
      font-weight: 600;
    }
    p {
      color: $scarlet;
      margin-top: 0.5em;
      font-size: 0.9rem;
      font-weight: 600;
    }
  }
  .details {
    background-color: $white;
    font-weight: 300;
    color: $gray;
    padding: 2em 1em;
    font-size: 0.8rem;
    font-style: italic;

    border: none;

    li {
      margin-bottom: 1em;
    }
  }

  button {
    width: 100%;
    padding: 1em 0;
    background-color: $scarlet;
    color: $white;

    &:hover {
      transform: scaleY(1.2);
      transition: 300ms;
    }
  }
}

// .ticket:nth-child(2) {
//   position: relative;

//   &::after {
//     content: "Featured!";
//     position: absolute;
//     // top: 17px;
//     // right: -50px;
//     inset: 0 0 auto 0;
//     font-size: 0.7rem;
//     background-color: $scarlet;
//     color: white;
//     padding: 0.5em 2.3em;
//     transform-origin: 100% 0;
//     transform: translate(29.3%) rotate(45deg);
//     overflow: hidden;
//     box-shadow: 0 0 0 999px $scarlet;
//     clip-path: inset(0 -100%);
//   }
//}
</style>

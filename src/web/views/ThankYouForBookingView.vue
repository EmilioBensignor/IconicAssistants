<template>
  <div class="h-100 column justify-space-between bg-grayBg">
    <section class="h-75 justifyCenter">
      <nav class="justifyCenter py-5">
        <IconicLogo class="align-self-center mt-1" color="blue" />
      </nav>
      <div class="w-75 flexCenter mt-5">
        <p>Thank you for booking a call.</p>
        <p>See you soon!</p>
        <router-link class="secondaryButton elevation-5 mt-10" :to="routes.HOME">Return to Homepage</router-link>
      </div>
    </section>
    <div class="columnAlignCenter">
      <FooterRightsComponent />
    </div>
  </div>
</template>

<script>
import ROUTES_NAMES from "@/router/constants/ROUTES_NAMES";
import IconicLogo from "@/web/components/icons/IconicLogo.vue";
import FooterRightsComponent from "../components/FooterRightsComponent.vue";

export default {
  name: "ThankYouForBooking",
  components: {
    IconicLogo,
    FooterRightsComponent,
  },
  data() {
    return {
      routes: ROUTES_NAMES,
      currentYear: new Date().getFullYear()
    }
  },
};
</script>

<style scoped>
.footerBelow p,
.footerBelow a {
  font-size: 0.9rem;
  color: white;
  text-decoration: none;
}

.rightsReserved {
  font-size: 0.8rem;
}

/* SM */
@media only screen and (min-width: 480px) {

  .footerBelow p,
  .footerBelow a {
    font-size: 1rem;
  }

  .rightsReserved {
    font-size: 0.9rem;
  }
}

@media only screen and (min-width: 769px) {
  .footerBelow p,
  .footerBelow a {
    font-size: 1.05rem;
  }

  .rightsReserved {
    font-size: 1rem;
  }
}

/* Desktop */
@media only screen and (min-width: 1080px) {
  .rightsReserved {
    font-size: 1rem;
    margin-bottom: 3vw !important;
  }
}

@media only screen and (min-width: 1600px) {
  .rightsReserved {
    margin: 2vw 0 !important;
  }
}

@media only screen and (min-width: 1920px) {
  .rightsReserved {
    margin: 25px 0 !important;
  }
}
</style>
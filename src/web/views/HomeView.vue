<template>
  <HeaderContactComponent />
  <HeroComponent
    :action="buttonActions.hero.action"
    :linkTo="routes.CONTACT_US"
    :handleAction="handleAction" />
  <GetStartedComponent />
  <WhatCanComponent
    :action="buttonActions.whatCan.action"
    :linkTo="routes.CONTACT_US"
    :handleAction="handleAction" />
  <YouBenefitComponent />
  <YourReturnComponent />
  <MatchingProcessComponent />
  <StartDelegatingComponent
    :action="buttonActions.startDelegating.action"
    :linkTo="routes.CONTACT_US"
    :handleAction="handleAction" />
  <GoogleReviewsComponent />
  <FAQsComponent
    :action="buttonActions.faq.action"
    :linkTo="routes.CONTACT_US"
    :handleAction="handleAction" />
  <FooterContactComponent />
</template>

<script>
  import HeaderContactComponent from "@/web/components/contactUs/HeaderContactComponent.vue";
  import IconicLogo from "@/web/components/icons/IconicLogo.vue";
  import HeroComponent from "@/web/components/home/HeroComponent.vue";
  import GetStartedComponent from "@/web/components/contactUs/GetStartedComponent.vue";
  import WhatCanComponent from "@/web/components/contactUs/WhatCanComponent.vue";
  import YouBenefitComponent from "@/web/components/contactUs/YouBenefitComponent.vue";
  import YourReturnComponent from "@/web/components/contactUs/YourReturnComponent.vue";
  import MatchingProcessComponent from "@/web/components/contactUs/MatchingProcessComponent.vue";
  import StartDelegatingComponent from "@/web/components/contactUs/StartDelegatingComponent.vue";
  import GoogleReviewsComponent from "@/web/components/contactUs/GoogleReviewsComponent.vue";
  import FAQsComponent from "@/web/components/home/FAQsComponent.vue";
  import FooterContactComponent from "@/web/components/contactUs/FooterContactComponent.vue";

  import { computed } from "vue";
  import { useHead } from "@vueuse/head";
  import { useRoute } from "vue-router";
  import ROUTES_NAMES from "@/router/constants/ROUTES_NAMES";
  import { useButtonActions } from "@/web/composables/useButtonActions";

  export default {
    name: "ContactUs",
    components: {
      HeaderContactComponent,
      IconicLogo,
      HeroComponent,
      GetStartedComponent,
      WhatCanComponent,
      YouBenefitComponent,
      YourReturnComponent,
      MatchingProcessComponent,
      StartDelegatingComponent,
      GoogleReviewsComponent,
      FAQsComponent,
      FooterContactComponent,
    },
    data() {
      return {
        routes: ROUTES_NAMES,
      };
    },
    setup() {
      const route = useRoute();
      const { handleAction } = useButtonActions();
      useHead({
        title: computed(() => route.meta.title),
        meta: [
          {
            name: "description",
            content: computed(() => route.meta.description),
          },
        ],
      });
      const buttonActions = {
        hero: { action: "link" },
        whatCan: { action: "link" },
        startDelegating: { action: "link" },
        faq: { action: "link" },
      };
      return {
        handleAction,
        buttonActions,
      };
    },
  };
</script>

<style scoped>
  /* Desktop */
  @media only screen and (min-width: 1080px) {
    .secondaryButton {
      padding: 2vw 3.5vw;
    }
  }

  @media only screen and (min-width: 1200px) {
    .secondaryButton {
      padding: 1.75vw 3vw;
    }
  }

  @media only screen and (min-width: 1350px) {
    .secondaryButton {
      padding: 1.5vw 2.8vw;
    }
  }

  @media only screen and (min-width: 1550px) {
    .secondaryButton {
      padding: 1.2vw 2.5vw;
    }
  }

  @media only screen and (min-width: 1750px) {
    .secondaryButton {
      padding: 1.2vw 2.2vw;
    }
  }

  @media only screen and (min-width: 1920px) {
    .secondaryButton {
      padding: 21px 42px;
    }
  }
</style>

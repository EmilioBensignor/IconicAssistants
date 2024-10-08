<template>
  <section class="radioactiveWaves bg-grayBg">
    <div class="w-100 content empowerWrapper flexCenter ga-15 mt-5 mb-15">
      <div
        v-for="(item, index) in empower"
        :key="index"
        v-motion="scrollBottom"
        class="empower w-75">
        <img
          :src="getImgUrl(item.img)"
          :alt="item.alt"
          class="shadow-3 mb-n15"
          width="60%" />
        <div
          class="empowerBody flexCenter bg-radioactive rounded-te-xl rounded-bs-xl elevation-5 mt-n3 pt-15 pa-5">
          <h3 class="text-white mt-2">{{ item.title }}</h3>
          <p class="subtitle font-weight-bold text-white">
            {{ item.subtitle }}
          </p>
          <ul class="mt-5 column ga-3">
            <li
              v-for="(advantage, index) in item.advantages"
              :key="index"
              class="mx-1"
              v-html="advantage"></li>
          </ul>
          <v-expansion-panels class="moreInfo mt-3">
            <v-expansion-panel
              class="bg-radioactive mt-3 elevation-3"
              title="More Info"
              :text="item.moreInfo">
            </v-expansion-panel>
          </v-expansion-panels>
        </div>
      </div>
    </div>
    <p v-motion="scrollBottom" class="partner font-weight-bold mt-10">
      Partner with us for a transformative experience.
    </p>
    <router-link
      class="w-50 secondaryButton my-3 elevation-5"
      :to="'/contact-us'"
      >Contact Us</router-link
    >
  </section>
</template>

<script>
  export default {
    data() {
      return {
        empower: [
          {
            img: "Recruitment-Expertise-Pre-Vetted-Proffesionals.png",
            alt: "Recruitment Expertise Pre-Vetted Proffesionals",
            title: "Recruitment:",
            subtitle: "The Power of Expertise",
            advantages: [
              "<span class='font-weight-bold'>Efficiency:</span> Streamlined recruitment process.",
              "<span class='font-weight-bold'>Thoroughness:</span> Background checks and <span class='font-weight-bold'>PDA Assessment.</span>",
              "<span class='font-weight-bold'>Rapid Acquisition:</span> 5 to 7 days for the perfect match.",
            ],
            moreInfo:
              "Entrust recruitment complexity to our seasoned HR team. With decades of expertise, our talent pool of vetted remote professionals ensures swift acquisition, taking just 5 to 7 days. Experience success with our guiding team.",
          },
          {
            img: "Global-Payroll-Executive-Assistant.png",
            alt: "Global Payroll Executive Assistant",
            title: "Payroll:",
            subtitle: "Seamlessly Global",
            advantages: [
              "<span class='font-weight-bold'>Global Reach:</span> Payroll services for remote talent worldwide.",
              "<span class='font-weight-bold'>Cost Efficiency:</span> One transparent fee for any number of hires.",
              "<span class='font-weight-bold'>Peace of Mind:</span> Trustworthy payroll management.",
            ],
            moreInfo:
              "Our payroll services transcend borders. Irrespective of your remote talent's location or hiring scale, we charge a single, transparent fee. Simplify financial operations while we handle payroll precisely.",
          },
          {
            img: "Compliance-Outsource-Executive-Assistant.png",
            alt: "Compliance Outsource Executive Assistant",
            title: "Support and Compliance:",
            subtitle: "Your Success, Our Priority",
            advantages: [
              "<span class='font-weight-bold'>Dedicated Support:</span> Client Success Agents for personalized assistance.",
              "<span class='font-weight-bold'>Compliance Assurance:</span> Meeting regulatory requirements.",
              "<span class='font-weight-bold'>Flexibility:</span> Seamless talent changes without extra fees.",
            ],
            moreInfo:
              "Smooth client-talent relationships are our priority. Each client gets a dedicated Success Agent, fostering communication with periodic reports and prompt issue resolution. We ensure compliance and offer flexibility for evolving needs without extra fees.",
          },
        ],
      };
    },
    methods: {
      getImgUrl(imgName) {
        return new URL(
          `../../assets/images/services/${imgName}`,
          import.meta.url
        ).href;
      },
    },
  };
</script>

<script setup>
  import { scrollBottom } from "@/motions.js";
</script>

<style scoped>
  .moreInfo {
    width: 85%;
  }

  /* SM */
  @media only screen and (min-width: 480px) {
    .empower img {
      width: 50%;
    }

    .moreInfo {
      width: 90%;
    }
  }

  /* MD */
  @media only screen and (min-width: 769px) {
    .empower {
      width: 50% !important;
    }
  }

  /* Desktop */
  @media only screen and (min-width: 1080px) {
    .empowerWrapper {
      width: 90% !important;
      gap: 15vw !important;
      margin-top: 5vw !important;
    }

    .empower {
      width: 100% !important;
      display: flex;
      flex-direction: row-reverse;
      justify-content: flex-end;
      gap: 5vw !important;
      position: relative;
      padding-right: 5vw;
      margin-left: 5vw;
    }

    .empowerWrapper .empower:nth-child(2) {
      flex-direction: row;
      padding-right: 0 !important;
      padding-left: 5vw;
      margin-left: 0 !important;
      margin-right: 5vw;
    }

    .empower img {
      width: 35%;
      position: absolute;
      right: 0;
      top: 2vw;
      z-index: 2;
    }

    .empowerWrapper .empower:nth-child(2) img {
      left: 1vw;
    }

    .empowerBody {
      width: 85%;
      align-items: flex-start;
      text-align: start;
      padding-top: 1vw !important;
      padding-right: 5vw !important;
    }

    .empowerWrapper .empower:nth-child(2) .empowerBody {
      padding-left: 11vw !important;
    }

    .empowerBody ul {
      width: 90%;
      list-style: circle;
      padding-left: 3vw;
    }

    .empowerWrapper .empower:nth-child(2) .empowerBody ul {
      width: 95%;
    }

    .empowerWrapper .empower:nth-child(2) .moreInfo {
      width: 90%;
    }

    .moreInfo {
      width: 80%;
    }

    .partner {
      font-size: 1.3rem;
    }

    .secondaryButton {
      width: auto !important;
      padding: 2.2vw 5.5vw;
    }
  }

  @media only screen and (min-width: 1280px) {
    .empowerBody ul {
      width: 85%;
    }

    ul li {
      font-size: 1.1rem;
    }
  }

  @media only screen and (min-width: 1350px) {
    .partner {
      margin-top: 7vw !important;
    }
  }

  @media only screen and (min-width: 1600px) {
    .empowerBody {
      padding-left: 1.5vw !important;
    }

    ul li {
      font-size: 1.2rem;
    }

    .partner {
      font-size: 1.4rem;
      margin: 7vw 0 1vw 0 !important;
    }
  }

  @media only screen and (min-width: 1650px) {
    .partner {
      margin-top: 10vw !important;
    }
  }

  @media only screen and (min-width: 1750px) {
    .empowerWrapper {
      gap: 12vw !important;
    }

    .empower img {
      width: 25%;
      right: 10vw;
      top: 5vw;
    }

    .empowerWrapper .empower:nth-child(2) .empowerBody {
      padding-left: 9vw !important;
    }

    .empowerWrapper .empower:nth-child(2) img {
      left: 5vw;
    }

    .partner {
      font-size: 1.5rem;
      margin: 8vw 0 1vw 0 !important;
    }
  }

  @media only screen and (min-width: 1920px) {
    .empowerWrapper {
      gap: 17.5rem !important;
      margin-top: 7.5% !important;
    }

    .empowerBody {
      width: 75%;
    }

    .empower {
      gap: 100px !important;
      padding-right: 200px;
      margin-left: 350px;
    }

    .empower img {
      right: 350px;
      top: 80px;
    }

    .empowerWrapper .empower:nth-child(2) {
      padding-left: 200px;
      margin-right: 400px;
    }

    .empowerWrapper .empower:nth-child(2) img {
      left: 330px;
    }

    .secondaryButton {
      padding: 30px 75px;
    }

    .partner {
      margin-top: 155px !important;
    }
  }
</style>

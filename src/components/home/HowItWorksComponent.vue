<template>
  <section class="skyRadioactiveWaves">
    <p v-motion="scrollBottom" class="subtitle text-radioactive">
      How It Works
    </p>
    <h2 v-motion="scrollBottom" class="text-midnight">
      How Our <span class="text-radioactive">Remote Talent Service</span> Works
    </h2>
    <div class="works columnAlignCenter ga-10 mt-5 mb-3">
      <div class="w-75 step12 columnAlignCenter ga-10">
        <div
          v-for="(item, index) in steps.slice(0, 2)"
          :key="index"
          v-motion="scrollBottom"
          class="step rounded-xl pa-3 pb-6 elevation-5 columnAlignCenter ga-3">
          <p class="text-radioactive w-100 ml-3 stepNumbers">
            {{ item.number }}
          </p>
          <v-img
            eager
            :src="getImgUrl(item.img)"
            :alt="item.alt"
            class="shadow-2"
            width="45%"></v-img>
          <p class="stepTitle">{{ item.title }}</p>
          <p class="stepBody">{{ item.body }}</p>
        </div>
      </div>
      <div class="desktopImg" v-motion="scrollBottom">
        <img
          src="@/assets/images/misc/Remote-Talent-Four-Steps.png"
          alt="Remote Talent Four Steps"
          width="90%" />
      </div>
      <div class="step34 columnAlignCenter ga-10">
        <div
          v-for="(item, index) in steps.slice(2)"
          :key="index + 2"
          v-motion="scrollBottom"
          class="w-75 step reversed rounded-xl pa-3 pb-6 elevation-5 columnAlignCenter ga-3">
          <p class="text-radioactive w-100 ml-3 stepNumbers reversed">
            {{ item.number }}
          </p>
          <v-img
            eager
            :src="getImgUrl(item.img)"
            :alt="item.alt"
            class="shadow-2"
            width="45%"></v-img>
          <p class="stepTitle">{{ item.title }}</p>
          <p class="stepBody">{{ item.body }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
  import { scrollBottom } from "@/motions.js";
</script>

<script>
  export default {
    data() {
      return {
        steps: [
          {
            number: "1.",
            img: "misc/Book-Appointment.png",
            alt: "Book an Appointment",
            title: "Book an Appointment",
            body: "Share all the essential details about your business and specify the tasks you'd like to assign.",
          },
          {
            number: "2.",
            img: "misc/Pre-vetted-Recruitment.png",
            alt: "Pre-vetted Recruitment",
            title: "Recruitment",
            body: "We'll identify the top VAs for you and our HR Manager will handle your VA interviews.",
          },
          {
            number: "3.",
            img: "misc/Onboarding-Expertise.png",
            alt: "Onboarding Expertise",
            title: "Onboarding",
            body: "We'll guide you through the onboarding process to ensure your VA integrates smoothly into your business.",
          },
          {
            number: "4.",
            img: "misc/Ongoing-Support.png",
            alt: "Ongoing Support",
            title: "Ongoing Support",
            body: "After selecting your VA, we'll take care of all HR-related matters, including payroll and performance reviews.",
          },
        ],
      };
    },
    methods: {
      getImgUrl(imgName) {
        return new URL(`../../assets/images/${imgName}`, import.meta.url).href;
      },
    },
  };
</script>

<style scoped>
  .desktopImg {
    display: none;
  }
  .step {
    background-color: rgb(12, 185, 241, 0.2);
  }
  .stepNumbers {
    text-align: start;
    font-weight: 700;
    font-size: 1.5rem;
  }

  .stepTitle {
    font-weight: 600;
    font-size: 1.2rem;
  }

  .stepBody {
    font-size: 1rem;
  }

  /* SM */
  @media only screen and (min-width: 480px) {
    .works {
      width: 75% !important;
    }
    .stepNumbers {
      font-size: 1.7rem;
    }
    .stepTitle {
      font-size: 1.3rem;
    }
  }

  /* MD */
  @media only screen and (min-width: 769px) {
    .works {
      width: 50% !important;
    }
    .stepNumbers {
      font-size: 1.8rem;
    }
    .stepTitle {
      font-size: 1.4rem;
    }
  }

  /* LG */
  @media only screen and (min-width: 992px) {
    .works {
      width: 95% !important;
      display: grid !important;
      grid-template-columns: repeat(3, 1fr);
      grid-template-rows: 1fr;
      justify-items: center;
    }
    .step12 {
      grid-area: 1 / 1 / 2 / 2;
    }
    .desktopImg {
      display: block;
      grid-area: 1 / 2 / 2 / 3;
    }
    .step34 {
      grid-area: 1 / 3 / 2 / 4;
    }
    .step {
      height: 35vh;
      width: 100% !important;
      text-align: start;
      box-shadow: none !important;
      background: none !important;
    }
    .reversed {
      text-align: end !important;
    }
    .stepNumbers {
      margin: 0 !important;
    }
    .stepTitle {
      width: 100%;
      font-weight: bold;
    }
    .stepBody {
      width: 100%;
    }
    .step .v-img {
      display: none;
    }
  }

  /* Desktop */
  @media only screen and (min-width: 1080px) {
    .step {
      height: 33vh;
    }
  }
</style>

<template>
  <div class="content">
    <div class="columnAlignCenter">
      <h2 v-motion="scrollBottom" class="simpleTitle text-white my-3">Finding an Executive Assistant is More SIMPLE Than
        Ever</h2>
      <p v-motion="scrollBottom" class="simpleSubtitle explication text-white mb-4">
        Whether you need part-time or full-time help, ICONIC is the <span class='font-weight-bold'>quickest way</span>
        to
        get your own
        <span class='font-weight-bold'>dedicated EA</span>.
      </p>
      <div class="columnAlignCenter ga-15 py-10">
        <div v-motion="scrollBottom" class="simple w-75 columnAlignCenter ga-5">
          <img width="100%" height="100%" class="rounded-xl elevation-5"
            src="@/web/assets/images/contactUs/Discovery-Simple.png" alt="Discovery">
          <div class="simpleBody columnAlignCenter ga-3">
            <p class="titleContact text-white font-weight-bold">Discovery</p>
            <p class="text-white">
              Schedule a <span class="font-weight-bold">quick 15-minute call</span> to discuss your business <span
                class="font-weight-bold">needs</span> and the attributes you are looking for in an ideal <span
                class="font-weight-bold">executive assistant</span>. Share information on the essential skills,
              experience,
              and criteria required. Determine if our recruitment approach and services align with your <span
                class="font-weight-bold">requirements</span>.</p>
          </div>
        </div>
        <div v-motion="scrollBottom" class="simple reversed w-75 columnAlignCenter ga-5">
          <img width="100%" height="100%" class="rounded-xl elevation-5"
            src="@/web/assets/images/contactUs/Matching-Simple.png" alt="Onboarding">
          <div class="simpleBody columnAlignCenter ga-3">
            <p class="titleContact text-white font-weight-bold">Matching</p>
            <p class="text-white">
              Next, our <span class="font-weight-bold">Matching team</span> will <span
                class="font-weight-bold">meticulously
                analyse</span> your requirements and objectives to match you with an <span
                class="font-weight-bold">Exceptional Assistant</span> who will align perfectly with your needs. With a
              diverse pool of over <span class="font-weight-bold">10,000 pre-vetted assistants</span> specializing in
              various fields such as <span class="font-weight-bold">customer service</span>, bookkeeping, market
              research,
              virtual assistance, and more, we are confident that we can <span class="font-weight-bold">find the ideal
                match
                for you</span>.</p>
          </div>
        </div>
        <div v-motion="scrollBottom" class="simple w-75 columnAlignCenter ga-5">
          <img width="100%" height="100%" class="rounded-xl elevation-5"
            src="@/web/assets/images/contactUs/Onboarding-Simple.png" alt="Onboarding">
          <div class="simpleBody columnAlignCenter ga-3">
            <p class="titleContact text-white font-weight-bold">Onboarding</p>
            <p class="text-white">
              We'll hold your hand through the onboarding process so your EA can <span class="font-weight-bold">fit
                seamlessly into your business</span>. Our goal is to make the transition <span
                class="font-weight-bold">smooth and stress-free</span> for both you and your Executive Assistant. From
              setting up initial meetings to providing <span class="font-weight-bold">training and guidance</span>, we
              are
              committed to ensuring that your EA integrates <span class="font-weight-bold">smoothly</span> into your
              team.
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { scrollBottom } from "@/motions.js";
</script>

<style scoped>
.simple img {
  object-fit: cover;
}

.simpleBody p {
  width: 100% !important;
}

/* SM */
@media only screen and (min-width: 480px) {
  .simple img {
    width: 95%;
  }
}

@media only screen and (min-width: 600px) {
  .simple img {
    width: 85%;
  }
}

/* MD */
@media only screen and (min-width: 769px) {
  .simple img {
    width: 75%;
  }
}

/* LG */
@media only screen and (min-width: 992px) {
  .simple img {
    width: 65% !important;
  }
}

/* Desktop */
@media only screen and (min-width: 1080px) {
  .reversed {
    flex-direction: row-reverse !important;
  }

  .simpleTitle {
    text-align: start;
  }

  .simpleSubtitle {
    width: 85% !important;
    text-align: start;
  }

  .simple {
    flex-direction: row;
    gap: 2rem !important;
  }

  .simple img {
    width: 45% !important;
  }

  .simpleBody {
    text-align: start;
  }
}

/* XL */
@media only screen and (min-width: 1440px) {
  .simple img {
    width: 40% !important;
  }
}

@media only screen and (min-width: 1750px) {
  .simple img {
    width: 35% !important;
  }
}
</style>
<template>
  <HeaderPagesComponent />
  <section class="heroPagesRadioactiveWave">
    <div class="heroPages flexCenter">
      <h1 v-motion="scrollBottom" class="text-midnight">
        Hiring Excellence At
        <span class="text-radioactive">Iconic Assistants</span>
      </h1>
    </div>
  </section>
  <ExceptionalSkillComponent />
  <OutsourceTopComponent />
  <CandidateCriteriaComponent />
</template>

<script>
  import HeaderPagesComponent from "@/components/HeaderPagesComponent.vue";
  import ExceptionalSkillComponent from "@/components/howWeHire/ExceptionalSkillComponent.vue";
  import OutsourceTopComponent from "@/components/howWeHire/OutsourceTopComponent.vue";
  import CandidateCriteriaComponent from "@/components/howWeHire/CandidateCriteriaComponent.vue";

  export default {
    components: {
      HeaderPagesComponent,
      ExceptionalSkillComponent,
      OutsourceTopComponent,
      CandidateCriteriaComponent,
    },
  };
</script>

<script setup>
  import { scrollBottom } from "@/motions.js";
</script>

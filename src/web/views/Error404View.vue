<template>
  <HeaderPagesComponent />
  <section class="heroPagesRadioactiveWave columnAlignCenter">
    <div class="heroPages flexCenter ga-5">
      <h1 class="text-midnight">Something went wrong</h1>
      <p>Click the button below to go back to the home</p>
      <router-link class="secondaryButton" :to="'/'">Go to Home</router-link>
    </div>
  </section>
  <FooterComponent />
</template>

<script>
  import HeaderPagesComponent from "@/web/components/HeaderPagesComponent.vue";
  import FooterComponent from "@/web/components/FooterComponent.vue";

  import { computed } from "vue";
  import { useHead } from "@vueuse/head";
  import { useRoute } from "vue-router";

  export default {
    name: "Error404",
    components: {
      HeaderPagesComponent,
      FooterComponent,
    },
    setup() {
      const route = useRoute();
      useHead({
        title: computed(() => route.meta.title),
        meta: [
          {
            name: "description",
            content: computed(() => route.meta.description),
          },
        ],
      });
    },
  };
</script>

<template>
  <HeaderSuiteComponent />
  <div class="heroSuite columnAlignCenter ga-3">
    <router-link
      class="goBack rowCenter align-self-start ga-1 ml-3"
      :to="routes.ASSISTANTS">
      <v-icon icon="mdi-keyboard-backspace" color="radioactive"></v-icon>
      <p class="w-auto text-radioactive">Go back</p>
    </router-link>
    <h1 class="text-midnight ml-4" v-if="assistantData">
      {{ assistantData.firstname }} {{ assistantData.lastname }} Tasks
    </h1>
  </div>
  <div class="suiteComponents mt-5">
    <v-skeleton-loader
      class="w-75 mt-3"
      v-if="!assistantData && loading"
      type="card"></v-skeleton-loader>
    <div class="mt-3 mb-5" v-if="assistantData && !loading">
      <AssistantTaskTableComponent
        :tasks="assistantData.tasks"
        :assistantId="assistantData.id" />
    </div>
  </div>
</template>

<script>
  import { doc, getDoc } from "firebase/firestore";
  import { db } from "../firebase/init";
  import router from "@/router";
  import ROUTES_NAMES from "@/router/constants/ROUTES_NAMES";
  import { formatDate } from "../services/format.service";

  import HeaderSuiteComponent from "../components/HeaderSuiteComponent.vue";
  import AssistantTaskTableComponent from "../components/assistants/AssistantTaskTableComponent.vue";
  import { useAuthStore } from "../stores/auth.store";

  export default {
    data() {
      return {
        routes: ROUTES_NAMES,
        assistantId: this.$route.params.id,
        assistantData: null,
        loading: true,
        store: useAuthStore(),
      };
    },
    components: {
      HeaderSuiteComponent,
      AssistantTaskTableComponent,
    },

    watch: {
      "store.assistants": {
        handler(newValue) {
          if (newValue && newValue.data && newValue.data.assistants) {
            this.assistantData = newValue.data.assistants.find(
              (assistant) => assistant.id === this.assistantId
            );
            if (this.assistantData) {
              this.loading = false;
            } else {
              router.push(ROUTES_NAMES.ASSISTANTS);
            }
          }
        },
        immediate: true, // Run handler immediately if the data is already present
      },
    },
    setup() {
      formatDate();
    },
  };
</script>

<style scoped>
  .goBack {
    text-decoration: none;
  }
</style>

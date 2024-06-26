<template>
  <section class="skyRadioactive">
    <div class="content">
      <div class="columnAlignCenter">
        <h2 v-motion="scrollBottom" class="text-white">Benefits</h2>
        <p v-motion="scrollBottom" class="w-75 companies text-white mt-3">
          Companies are increasingly mutating towards predominantly executive
          assistants instead of in-house employees due to several compelling
          reasons:
        </p>
        <div class="w-75 twoBenefits columnAlignCenter ga-5 my-5">
          <div class="w-100 columnAlignCenter ga-5">
            <v-expansion-panels
              v-for="(item, index) in benefitsLeft"
              :key="index"
              v-motion="scrollBottom"
              class="faqWrapper">
              <v-expansion-panel
                class="elevation-2"
                :title="item.title"
                :text="item.text"
                expand-icon="mdi-plus"
                collapse-icon="mdi-minus">
              </v-expansion-panel>
            </v-expansion-panels>
          </div>
          <div class="w-100 columnAlignCenter ga-5">
            <v-expansion-panels
              v-for="(item, index) in benefitsRight"
              :key="index"
              v-motion="scrollBottom"
              class="faqWrapper">
              <v-expansion-panel
                class="elevation-2"
                :title="item.title"
                :text="item.text"
                expand-icon="mdi-plus"
                collapse-icon="mdi-minus">
              </v-expansion-panel>
            </v-expansion-panels>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
  export default {
    data() {
      return {
        benefitsLeft: [
          {
            title: "Cost Efficiency",
            text: "Utilizing remote iconic executive assistants often proves more cost-effective for businesses. It eliminates expenses related to physical office spaces, utilities, and other infrastructure costs associated with in-house employees.",
          },
          {
            title: "Flexibility and Scalability",
            text: "Iconic executive assistants offer a high degree of flexibility. Businesses can scale their workforce up or down based on project demands without the constraints of physical office space or the need for extensive hiring and onboarding processes.",
          },
          {
            title: "Advancements in Technology",
            text: "Advancements in communication and collaboration technology have made it easier to manage remote teams. Video conferencing, project management tools, and other executive collaboration platforms ensure seamless communication and coordination.",
          },
          {
            title: "Efficiency and Productivity",
            text: "Remote work models can enhance efficiency and productivity. Executive assistants can work in environments that suit their individual productivity preferences, contributing to improved work outcomes.",
          },
          {
            title: "Technological Integration",
            text: "Integration of artificial intelligence and automation allows executive assistants to handle a diverse range of tasks efficiently. This technological integration enhances the value proposition of executive assistants for companies seeking streamlined operations.",
          },
        ],
        benefitsRight: [
          {
            title: "Global Talent Access",
            text: "Iconic executive assistants enable companies to tap into a global talent pool. This broader access allows businesses to find specialized skills and expertise that may not be readily available in their local vicinity.",
          },
          {
            title: "Adaptability to Modern Work",
            text: "Modern work preferences are shifting towards flexibility and remote options. Offering executive assistant roles aligns with this trend, making it easier for companies to attract and retain talent by accommodating diverse work preferences.",
          },
          {
            title: "Evolving Work Models",
            text: "The traditional 9-to-5 work model is evolving. Iconic executive assistants often work on a project or task basis, emphasizing output and results over a fixed work schedule, aligning with the changing dynamics of modern work.",
          },
          {
            title: "Risk Mitigation",
            text: "Remote models provide a level of risk mitigation. Companies can distribute their workforce across different locations, reducing the impact of regional disruptions, such as natural disasters or localized economic downturns.",
          },
          {
            title: "Crisis Preparedness",
            text: "The COVID-19 pandemic highlighted the importance of remote work as a crisis-resilient strategy. Companies with established remote models were better equipped to navigate disruptions and ensure business continuity.",
          },
        ],
      };
    },
  };
</script>

<script setup>
  import { scrollBottom } from "@/motions.js";
</script>

<style scoped>
  /* Desktop */
  @media only screen and (min-width: 1080px) {
    .companies {
      width: 60% !important;
      font-size: 1.25rem;
    }

    .twoBenefits {
      display: flex;
      flex-direction: row;
      padding-bottom: 5vw;
    }
  }

  /* XL */
  @media only screen and (min-width: 1440px) {
    .twoBenefits {
      margin-top: 2.5vw !important;
      padding-bottom: 7vw;
    }
  }

  @media only screen and (min-width: 1920px) {
    .twoBenefits {
      margin-top: 40px !important;
      padding-bottom: 100px;
    }
  }
</style>

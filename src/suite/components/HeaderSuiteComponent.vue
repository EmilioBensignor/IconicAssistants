<template>
  <nav class="mb-15">
    <v-app-bar elevation="0" app class="bg-white d-flex align-center py-1">
      <v-app-bar-nav-icon
        icon="mdi-menu"
        color="radioactive"
        class="hamburger shadow-15"
        size="x-large"
        @click="showMenu = !showMenu">
      </v-app-bar-nav-icon>
      <v-toolbar-title>
        <router-link class="text-decoration-none" :to="'/'">
          <img
            width="75%"
            src="@/suite/assets/images/Suite-Logo.png"
            alt="Suite Logo" />
        </router-link>
      </v-toolbar-title>
      <v-menu>
        <template v-slot:activator="{ props }">
          <v-btn
            class="account bg-radioactive elevation-3 pa-1"
            icon="mdi-account"
            v-bind="props">
          </v-btn>
        </template>
        <v-list class="mt-1 py-0">
          <v-list-item v-for="(item, index) in accountMenu" :key="index">
            <router-link :to="item.path">
              <v-list-item-title class="text-radioactive">
                {{ item.title }}
              </v-list-item-title>
            </router-link>
          </v-list-item>
          <v-list-item @click="onLogout">
            <v-list-item-title class="text-radioactive"
              >Logout</v-list-item-title
            >
          </v-list-item>
        </v-list>
      </v-menu>
    </v-app-bar>
    <v-navigation-drawer v-model="showMenu" app class="mt-2">
      <v-list class="py-0" tag="ul">
        <li v-for="item in suiteMenu" :key="item.title">
          <v-list-item :to="item.path">
            <div class="d-flex align-center">
              <v-icon color="radioactive" :icon="`mdi-${item.icon}`"></v-icon>
              <v-list-item-title class="pl-4 text-midnight">
                {{ item.title }}
              </v-list-item-title>
            </div>
          </v-list-item>
        </li>
      </v-list>
    </v-navigation-drawer>
  </nav>
</template>

<script>
  import routes from "@/router/constants/ROUTES_NAMES";
  import { logout } from "@/suite/services/auth.service";

  export default {
    name: "HeaderSuiteComponent",
    data() {
      return {
        showMenu: false,
        suiteMenu: [
          {
            path: routes.SUITE,
            title: "DASHBOARD",
            icon: "home",
          },
          {
            path: routes.ASSISTANTS,
            title: "ASSISTANS",
            icon: "account-group",
          },
          {
            path: routes.INVOICES,
            title: "INVOICES",
            icon: "receipt",
          },
        ],
        accountMenu: [
          {
            path: routes.ACCOUNT,
            title: "Account",
          },
          {
            path: routes.PAYMENT_METHODS,
            title: "Payment Methods",
          },
        ],
      };
    },
    mounted() {
      window.addEventListener("scroll", this.handleScroll);
    },
    beforeDestroy() {
      window.removeEventListener("scroll", this.handleScroll);
    },
    methods: {
      handleScroll() {
        const scrollTop =
          window.pageYOffset || document.documentElement.scrollTop;
        const windowHeight = window.innerHeight;

        const threshold = windowHeight * 0.5;

        if (scrollTop >= threshold) {
          this.isScrolled = true;
        } else {
          this.isScrolled = false;
        }
      },
      onLogout() {
        logout();
      },
    },
  };
</script>

<style scoped>
  .v-app-bar {
    position: relative;
  }
  .account {
    position: absolute;
    right: 4%;
    cursor: pointer;
  }
  a {
    text-decoration: none;
  }
  .v-list-item:hover {
    background: #f6f6f6;
  }
  .v-menu .v-list-item-title {
    font-weight: 600;
  }
  .v-navigation-drawer .v-list-item-title {
    font-weight: 500;
  }
</style>
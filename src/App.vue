<template>
  <v-app>
    <v-app-bar app color="white" flat class="hidden-sm-and-down">
      <div class="d-flex ml-4">
        <v-img
          class="mr-2"
          contain
          src="@/assets/logo.png"
          transition="scale-transition"
          width="40"
        />
        <span class="mr-12 name">
          <span class="primary--text">L</span>AU<span class="primary--text"
            >R</span
          ><span>A MARTÍN</span>
        </span>
      </div>

      <div class="nav-menu" v-for="item in this.menu" :key="item.name">
        <v-btn text @click="scrollingTo(item.route)" class="mx-1">
          <span>{{ item.name }}</span>
        </v-btn>
      </div>

      <v-spacer></v-spacer>

      <v-btn
        href="https://www.linkedin.com/in/laura-mart%C3%ADn-vicente-7554a2208/"
        target="_blank"
        text
        class="nav-menu"
      >
        <v-icon class="primary--text">mdi-linkedin</v-icon>
        <span class="mr-2">Linked in</span>
      </v-btn>
    </v-app-bar>
    <Slide class="hidden-md-and-up" width="250">
      <a
        v-for="item in this.menu"
        :key="item.name"
        @click="scrollingTo(item.route)"
        class="itemList"
      >
        <v-icon class="white--text">mdi-{{ item.icon }}</v-icon>
        <span class="mr-2">{{ item.name }}</span>
      </a>
      <a
        class="itemList"
        href="https://www.linkedin.com/in/laura-mart%C3%ADn-vicente-7554a2208/"
        target="_blank"
      >
        <v-icon class="white--text">mdi-linkedin</v-icon>
        <span class="mr-2">Linked in</span>
      </a>
    </Slide>
    <Home class="mt-9 mt-sm-0" />
    <Projects />
    <Contact />
    <v-divider class="mt-16"></v-divider>
    <v-footer
    class="white pt-4 montserrat"
    >
      <v-card
        flat
        width="100%"
        class="text-center"
      >
        <v-card-text>
          <v-btn
            v-for="icon in icons"
            :key="icon.icon"
            class="mx-4 social-media-bg"
            icon
            large
            :href="icon.url"
            target="_blank"
          >
            <v-icon size="45px" class="primary--text social-media">
              {{ icon.icon }}
            </v-icon>
          </v-btn>
        </v-card-text>
        <v-divider class="divider"></v-divider>
        <v-card-text class="primary--text">
          {{ new Date().getFullYear() }}© — <strong>Laura Martín Vicente</strong>
        </v-card-text>
      </v-card>
    </v-footer>
  </v-app>
</template>

<script>
import { Slide } from "vue-burger-menu";
import Home from "./components/Home.vue";
import Projects from "./components/Portfolio.vue";
import Contact from "./components/Contact.vue";

export default {
  name: "App",

  components: {
    Slide,
    Home,
    Projects,
    Contact,
  },

  data: () => ({
    menu: [
      {
        name: "Inicio",
        route: "b",
        icon: "home",
      },
      {
        name: "Sobre mí",
        route: "about",
        icon: "information-outline",
      },
      {
        name: "Portfolio",
        route: "projects",
        icon: "lightbulb",
      },
      {
        name: "Contacto",
        route: "contact",
        icon: "email-outline",
      },
    ],
    icons: [
      {
        icon: "mdi-linkedin",
        url: "https://www.linkedin.com/in/laura-mart%C3%ADn-vicente-7554a2208/"
      },
      {
        icon: "mdi-github",
        url: "https://github.com/kryzzraq"
      }
    ]
  }),
  methods: {
    scrollingTo(route) {
      let coordY = document.getElementById(route).offsetTop;
      scroll({
        top: coordY - 70,
        behavior: "smooth",
      });
    },
  },
};
</script>

<style lang="scss" scoped>
.name {
  align-self: end;
  margin-bottom: -8px;
  font-size: 1.5rem;
  font-family: 'Montserrat', sans-serif;
  font-weight: 800;
  letter-spacing: 1px;
}
.nav-menu {
    margin-bottom: -1rem;
}
.social-media-bg {
  background-color: #1662ae;
  padding: 25px;
}
.social-media{
  border-radius: 5px;
  background-color: white;
}
.social-media:focus {
  color: transparent !important;
}
.divider {
  max-height: 400px !important;
  margin: 0px 14%;
  border-color: rgba(0, 0, 0, 0.1) !important;
}
</style>

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
        <span class="mr-16 name">
          <span class="primary--text">L</span>AU<span class="primary--text"
            >R</span
          ><span>A MARTÍN</span>
        </span>
      </div>

      <div class="nav-menu" v-for="item in this.menu" :key="item.name">
        <v-btn text @click="scrollingTo(item.route)" class="mx-1">
          <span >{{ item.name }}</span>
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
      <a class="itemList">
        <v-icon class="white--text">mdi-linkedin</v-icon>
        <span class="mr-2">Linked in</span>
      </a>
    </Slide>
    <Home class="mt-9 mt-md-0" />
  </v-app>
</template>

<script>
import Home from "./components/Home.vue";
import { Slide } from "vue-burger-menu";

export default {
  name: "App",

  components: {
    Home,
    Slide,
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
        route: "b",
        icon: "lightbulb",
      },
      {
        name: "Contacto",
        route: "",
        icon: "email-outline",
      },
    ],
  }),
  methods: {
    scrollingTo(route) {
      let coordY = document.getElementById(route).offsetTop;
      scroll({
        top: coordY-70,
        behavior: "smooth"
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
  font-weight: 600;
}
.nav-menu {
  margin-bottom: -1rem;
}
.bm-burger-button {
  border: 10px solid white;
  border-radius: 24px;
  z-index: 1;
}
</style>

<template>
  <v-container class="montserrat">
    <section class="px-6" id="projects" ref="projects">
      <div class="about secondary--text">
        <div>Mi portfolio<span class="primary--text">:</span></div>
      </div>
      <article class="">
        <v-expansion-panels popout>
          <v-expansion-panel v-for="item in this.projects" :key="item.name">
            <v-expansion-panel-header class="primary--text text-button">
              {{ item.name }}
            </v-expansion-panel-header>
            <a :href="goGitHub(item)" target="_blank">
              <v-expansion-panel-content>
                <div class="description">
                  {{ item.description }}
                </div>
                <div class="d-flex">
                  <v-img
                    v-for="tech in item.tech"
                    :key="tech.name"
                    max-height="30"
                    max-width="30"
                    class="ma-1"
                    contain
                    :src="getLogoUrl(tech)"
                  ></v-img>
                </div>
              </v-expansion-panel-content>
            </a>
          </v-expansion-panel>
        </v-expansion-panels>
      </article>
    </section>
  </v-container>
</template>
´
<script>
export default {
  name: "Portfolio",
  components: {},
  data: () => ({
    projects: [
      {
        name: "Making Wishes",
        description:
          "App que permite tener una lista de deseos, tanto personal como en grupo con otras personas, como una lista de bodas por ejemplo.",
        github: "MakingWishes",
        tech: [
          {
            name: "slim",
            route: "slim.png",
          },
          {
            name: "vue",
            route: "vue.svg",
          },
          {
            name: "html5",
            route: "html5.png",
          },
          {
            name: "js",
            route: "js.png",
          },
        ],
      },
      {
        name: "Trivial web",
        description:
          "Juego sobre preguntas y respuestas guardadas en ficheros CSV.",
        github: "trivial",
        tech: [
          {
            name: "php",
            route: "php.png",
          },
          {
            name: "csv",
            route: "csv.svg",
          },
          {
            name: "html5",
            route: "html5.png",
          },
          {
            name: "css3",
            route: "css3.png",
          },
        ],
      },
      {
        name: "Ahorcado",
        description: "Clásico juego del ahocado.",
        github: "hangman",
        tech: [
          {
            name: "js",
            route: "js.png",
          },
          {
            name: "html5",
            route: "html5.png",
          },

          {
            name: "css3",
            route: "css3.png",
          },
        ],
      },
      {
        name: "Calculadora Web",
        description: "Calculadora Web con modo normal y modo científico.",
        github: "calculator",
        tech: [
          {
            name: "js",
            route: "js.png",
          },
          {
            name: "html5",
            route: "html5.png",
          },

          {
            name: "css3",
            route: "css3.png",
          },
        ],
      },
    ],
  }),
  methods: {
    getLogoUrl(item) {
      return require("../assets/tech-logos/" + item.route);
    },
    goGitHub(item) {
        return "https://github.com/kryzzraq/" + item.github;
    }
  },
};
</script>

<style scoped>
.about {
  font-weight: 600;
  font-size: 2.8rem;
}
a{
    text-decoration: none;
    color: rgba(0, 0, 0, 0.87) !important;;
}
</style>
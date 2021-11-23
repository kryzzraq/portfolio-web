<template>
  <v-container class="montserrat">
    <section class="px-1" id="projects" ref="projects">
      <div class="about secondary--text">
        <div>Mi portfolio<span class="primary--text">:</span></div>
      </div>
      <article class="px-1">
        <section>
          <p>
            A continuación puedes ver uno a uno los proyectos personales que he
            realizado en mi GitHub. Aunque si lo prefieres puedes verlo entero
            <v-tooltip bottom color="primary">
              <template v-slot:activator="{ on }">
                <span
                  class="
                    primary--text
                    font-weight-bold
                    text-decoration-underline
                  "
                  v-on="on"
                >
                  <a
                    href="https://github.com/kryzzraq"
                    class="font-weight-bold link"
                    target="_blank"
                    >aquí.</a
                  >
                </span>
              </template>
              <span>Ir a GitHub</span>
            </v-tooltip>
          </p>
          <v-expansion-panels popout class="my-8">
            <v-expansion-panel v-for="item in this.projects" :key="item.name">
              <v-expansion-panel-header class="primary--text text-button mt-1">
                {{ item.name }}
              </v-expansion-panel-header>
              <v-tooltip top color="primary" tag="div">
                <template v-slot:activator="{ on }">
                  <div v-on="on">
                    <a :href="goGitHub(item)" target="_blank" class="a-git">
                      <v-expansion-panel-content>
                        <div
                          class="
                            expansion-panel
                            d-flex
                            flex-row
                            justify-space-between
                            align-center
                          "
                        >
                          <div class="description mr-2">
                            {{ item.description }}
                          </div>
                          <div class="d-flex expansion-img">
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
                        </div>
                      </v-expansion-panel-content>
                    </a>
                  </div>
                </template>
                <span>Ver {{item.name}} en GitHub</span>
              </v-tooltip>
            </v-expansion-panel>
          </v-expansion-panels>
        </section>
        <section>
          <article
            class="px-1 d-flex justify-space-around flex-wrap align-center"
          >
            <lottie-player
              class="animation-reverse"
              src="https://assets10.lottiefiles.com/packages/lf20_9fluzcyn.json"
              background="transparent"
              mode="bounce"
              speed="0.75"
              style="width: 300px; height: 300px"
              loop
              autoplay
            ></lottie-player>
            <div class="behance-desc">
              Como mencioné antes, estoy formándome por mi cuenta diseño de
              interfaces y usabilidad. Quise estudiarlo para poder dar rienda
              suelta a mi creatividad haciendo bonitas, sencillas interfaces
              mientras mejoro la experiencia del usuario y, además, enfrentarme
              a un nuevo reto.
              <p class="mt-4">
                En
                <v-tooltip top color="primary">
                  <template v-slot:activator="{ on }">
                    <span
                      class="
                        primary--text
                        font-weight-bold
                        text-decoration-underline
                      "
                      v-on="on"
                    >
                      <a
                        href="https://www.behance.net/lauramartn16"
                        target="_blank"
                        class="font-weight-bold link"
                        >mi behance</a
                      >
                    </span>
                  </template>
                  <span>Ir a behance</span>
                </v-tooltip>
                podrás ver algunos de mis diseños.
              </p>
            </div>
          </article>
        </section>
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
        name: "API Making Wishes",
        description:
          "Api REST en PHP que se comunica con una bbdd relacional MySQL.",
        github: "API_making_wishes",
        tech: [
          {
            name: "slim",
            route: "slim.png",
          },
          {
            name: "sql",
            route: "mysql.png",
          },
        ],
      },
      {
        name: "Quiz-up!",
        description:
          "Juego de preguntas y respuestas guardadas en ficheros CSV.",
        github: "quiz-up",
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
        github: "hang-man",
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
        name: "Calculadora web",
        description: "Calculadora web con modo normal y modo científico.",
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
      {
        name: "Arte Origin",
        description:
          "Página web maquetada en HTML5 con Bootstrap de una galería de Arte.",
        github: "art-gallery",
        tech: [
          {
            name: "bootstrap",
            route: "bootstrap.svg",
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
        name: "Sugar Bloom",
        description:
          "Página web maquetada en HTML5 con y CSS3 usando grid de una pastelería.",
        github: "cake-shop",
        tech: [
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
    },
  },
};
</script>

<style scoped>
.about {
  font-weight: 600;
  font-size: 2.8rem;
}
.a-git {
  text-decoration: none;
  color: rgba(0, 0, 0, 0.87) !important;
}
.behance-desc {
  width: 60%;
}
.v-expansion-panel-header:hover, .v-expansion-panel-header {
  transition: 0.3s;
  color: #47a3ff !important;
}
@media (max-width: 870px) {
  .expansion-panel {
    flex-direction: column !important;
  }
  .expansion-img {
    margin-top: 10px;
  }
  .behance-desc {
    width: 100%;
  }
}
@media (max-width: 530px) {
  .expansion-img {
    align-self: center;
  }
}
</style>
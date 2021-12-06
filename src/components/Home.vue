<template>
  <v-container class="montserrat">
    <section class="d-flex align-center justify-center flex-column mt-16">
      <div class="presentation-bg"></div>
      <div class="presentation-bg-2"></div>
      <div class="subtitle">
        <div>FRONT-END</div>
        <div>DEVELOPER</div>
      </div>
      <div class="presentation secondary--text">
        <div class="ml-5 ml-sm-0">Hola<span class="primary--text">.</span></div>
        <div class="d-flex ml-5 ml-sm-0">
          <div>Soy</div>
          <div class="mini-text align-self-center ml-8 hidden-md-and-down">
            Desarrolladora <span class="primary--text">Front-End</span> y
            estudiante autodidacta de diseño
            <span class="primary--text">UI/UX.</span>
          </div>
        </div>
        <div class="ml-5 ml-sm-0">Laura</div>
        <div class="mini-text hidden-lg-and-up">
          Desarrolladora <span class="primary--text">Front-End</span> y
          estudiante autodidacta de diseño
          <span class="primary--text">UI/UX.</span>
        </div>
      </div>
    </section>
    <section id="about" class="px-1" ref="about">
      <div class="about secondary--text">
        <div>Mi historia<span class="primary--text">:</span></div>
      </div>
      <div class="px-1">
        <p>
          En el año 2019, tras estar muchos años trabajando, decidí cambiar de
          sector profesional al mundo IT que siempre me ha gustado. Comencé mi
          camino con el
          <span class="primary--text font-weight-bold"
            >CFGS: Desarrollo de Aplicaciones Web</span
          >. En este curso aprendí la base para desarrollarme profesionalmente
          en este ámbito.
        </p>
        <p>
          Actualmente, estoy estudiando de manera autodidacta diseño
          <v-tooltip bottom color="primary">
            <template v-slot:activator="{ on }">
              <span
                class="primary--text font-weight-bold text-decoration-underline"
                v-on="on"
              >
                UI/UX.
              </span>
            </template>
            <span>Interfaces y usabilidad</span>
          </v-tooltip>
          He decidido adentrarme en el diseño de interfaces para además de poder
          desarrollar el cliente de una web poder proponer mejoras y diseños
          fundamentados.
        </p>
      </div>
      <article class="px-1 d-flex justify-space-around flex-wrap align-center">
        <div class="skills primary white--text px-6 py-5">
          <span class="text-button">Skills</span>
          <ul class="px-7">
            <li v-for="item in this.mySkills" :key="item.name">
              {{ item.name }}
            </li>
          </ul>
        </div>
        <article class="skills-2">
          <lottie-player
            class="animation-reverse"
            src="https://assets7.lottiefiles.com/packages/lf20_ockwuxcf.json"
            background="transparent"
            speed="0.75"
            style="width: 300px; height: 300px"
            loop
            autoplay
          ></lottie-player>
        </article>
      </article>
      <article class="mt-5 px-1">
        <p>
          En el ámbito educativo comenzamos a dar nuestras primeras pinceladas
          en programación con Java. Ya en el segundo curso del ciclo vimos
          <span class="primary--text font-weight-bold"
            >JavaScript ES6, PHP y CSS3.</span
          >
          En el TFM del ciclo superior de Desarrollo de aplicaciones web utilicé
          <span class="primary--text font-weight-bold">SLIM framework</span>
          (PHP) para hacer una API sencilla y muy legible. Además usé
          <span class="primary--text font-weight-bold">VUE</span> para front,
          comenzando así mi estudio en este framework.
        </p>
        <p>
          En la actualidad estoy terminando de perfeccionar mis conocimientos de
          <span class="primary--text font-weight-bold">VUE</span> y estoy
          comenzando a estudiar
          <span class="primary--text font-weight-bold">React</span>. Cuando
          termine con React mis planes de futuro son estudiar
          <span class="primary--text font-weight-bold">Angular.</span>
        </p>
      </article>
    </section>
  </v-container>
</template>

<script>
export default {
  name: "Home",

  components: {},

  data: () => ({
    mySkills: [
      {
        name: "JavaScript ES6",
      },
      {
        name: "VUE",
      },
      {
        name: "PHP 8",
      },
      {
        name: "CSS3",
      },
      {
        name: "Java",
      },
      {
        name: "MySql",
      },
      {
        name: "MongoDB",
      },
    ],
  }),
};
</script>

<style lang="scss" scoped>
.presentation {
  font-weight: 600;
  font-size: 4.5rem;
  position: absolute;
  line-height: 1.2;
  z-index: 2;
}
.presentation-bg {
  position: absolute;
  right: -50px;
  height: 380px;
  background-image: url("../assets/background1.svg");
  background-size: contain;
  background-position: right;
  background-size: 60%;
  width: 100vw;
}
.presentation-bg-2 {
  position: absolute;
  left: -120px;
  height: 380px;
  background-image: url("../assets/background2.svg");
  background-size: contain;
  background-position: left;
  background-size: 60%;
  width: 100vw;
}
.mini-text {
  font-size: 1rem;
  height: 100%;
  width: 14rem;
  margin-top: 1rem;
}
.subtitle {
  color: rgb(209, 209, 209);
  font-weight: 600;
  font-size: 8rem;
  z-index: 1;
}
.about {
  margin-top: 0.4em;
  font-weight: 600;
  font-size: 2.8rem;
}
.skills {
  transition-duration: 0.5s;
  width: 15em;
  height: 15em;
  border-radius: 10px;
}
.skills:hover {
  transform: scale(1.1);
  transition-timing-function: cubic-bezier(0.47, 2.02, 0.31, -0.36);
}
.skills-2 {
  width: auto;
  height: auto;
  border-radius: 10px;
  margin-top: -5px;
}
.animation-reverse {
  transform: scaleX(-1);
}
@media (max-width: 870px) {
  .subtitle {
    font-size: 3.5rem;
    line-height: 1;
    height: 180px;
  }
  .presentation {
    font-size: 4rem;
  }
  .about {
    margin-top: 1.7em;
  }
  .presentation-bg,
  .presentation-bg-2 {
    background-size: 30.2em;
  }
  .presentation-bg-2 {
    left: -6em;
  }
}
@media (max-width: 530px) {
  .subtitle {
    font-size: 3rem;
    color: rgb(224, 224, 224);
  }
  .presentation {
    margin-top: 3rem;
    font-size: 3.5rem;
  }
  .about {
    margin-top: 2.5em;
  }
  .presentation-bg-2,
  .presentation-bg {
    background-size: 35em;
  }
  .presentation-bg-2 {
    left: -12.4em;
  }
  .presentation-bg {
    right: -8em;
  }
}
</style>

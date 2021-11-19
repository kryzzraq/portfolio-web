<template>
  <v-container class="montserrat">
    <section class="d-flex align-center justify-center flex-column mt-16">
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
    <section id="about" class="px-3" ref="about">
      <div class="about secondary--text">
        <div>Mi historia<span class="primary--text">:</span></div>
      </div>
      <div class="history-text">
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
    </section>
    <section
      class="px-3 d-flex justify-space-around flex-wrap-reverse align-center"
    >
      <article class="skills primary white--text pa-7">
        <span class="text-button">Skills</span>
        <ul class="px-7">
          <li v-for="item in this.mySkills" :key="item.name">
            {{ item.name }}
          </li>
        </ul>
      </article>
      <article class="skills-2">
        <lottie-player
          class="animation-reverse"
          src="https://assets6.lottiefiles.com/packages/lf20_yjxlc3cg.json"
          background="transparent"
          speed="1"
          style="width: 300px; height: 300px"
          loop
          autoplay
        ></lottie-player>
      </article>
    </section>
    <article class="mt-5 px-3">
      <p>
        En el ámbito educativo comenzamos a dar nuestras primeras pinceladas en
        programación con Java. Ya en el segundo curso del ciclo vimos
        <span class="primary--text font-weight-bold"
          >JavaScript ES6, PHP y CSS.</span
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
        empezando a comenzando a estudiar
        <span class="primary--text font-weight-bold">React</span>.
      </p>
    </article>
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
        name: "Python",
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
}
.mini-text {
  font-size: 1rem;
  height: 100%;
  width: 14rem;
  margin-top: 1rem;
}
.subtitle {
  color: rgb(241, 241, 241);
  font-weight: 600;
  font-size: 8rem;
}
.about {
  font-weight: 600;
  font-size: 3rem;
}
.skills {
  width: 15em;
  height: 15em;
  border-radius: 10px;
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
    font-size: 5rem;
  }
  .presentation {
    font-size: 4rem;
  }
  .about {
    margin-top: 1em;
  }
}
@media (max-width: 530px) {
  .subtitle {
    font-size: 3rem;
  }
  .presentation {
    margin-top: 3rem;
    font-size: 3.5rem;
  }
  .about {
    margin-top: 2.5em;
  }
}
</style>

<template>
  <v-container class="montserrat">
    <article id="contact" ref="contact" class="px-1">
      <div class="about secondary--text">
        <div>Mi contacto<span class="primary--text">:</span></div>
      </div>
      <section class="px-1">
        ¿Quiéres colaborar en algún proyecto? Ponte en contacto conmigo y
        cuéntame tus ideas.
        <p>¡Quizá podamos ayudarnos!</p>
      </section>
      <section class="mt-4 ml-1">
        Puedes contactar conmigo por email en:
        <a
          href="mailto:lauramartinv394@gmail.com"
          class="font-weight-bold link"
          >lauramartinv394@gmail.com</a
        >
        o contactar conmigo a través de linked in.
      </section>
    </article>
  </v-container>
</template>

<script>
export default {
  name: "Contact",
  components: {},
  data: () => ({}),
  methods: {},
};
</script>

<style scoped>
.about {
  font-weight: 600;
  font-size: 2.8rem;
}
</style>
<template>
  <div class="app">
    <Header />
    <Nuxt />
    <Footer />
  </div>
</template>

<script>
import { mapActions } from "vuex";
export default {
  created() {
    this.getPaginas();
  },
  methods: {
    ...mapActions({
      getPaginas: "conteudoApi/getPaginas",
    }),
  },
};
</script>

<style>
html,
body {
  width: 100%;
  height: auto;
  margin: 0;
  padding: 0;
}

.app {
  width: 100%;
  height: 100%;
}
</style>

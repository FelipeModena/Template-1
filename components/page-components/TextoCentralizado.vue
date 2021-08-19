<template>
  <div class="w-100 p-3 p-md-5 text-center  container-pagina-empresa">
    <h2>{{ componente.titulo }}</h2>
    <p class="w-100 py-2 text-left " v-html="componente.texto">
      {{ componente.texto }}
    </p>
  </div>
</template>

<script>
export default {
  props: {
    componente: {
      type: Object,
      default: () => {},
    },
  },
};
</script>

<style scoped>
  .container-pagina-empresa h3 {
    font-size: min(max(2.3rem, 4vw), 28px);
    font-weight: bold;
  }

  .container-pagina-empresa p {
    font-size: min(max(2rem, 3vw), 20px);
    padding: 0 20%;
  }

    @media (max-width: 768px) { 
    .container-pagina-empresa p {
      padding: 0 5%;
    }
  }
</style>

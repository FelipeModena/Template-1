<template>
  <button 
    class="custom-button-nuxt-link"
    :style="corBotao"
    @click="acessarPagina"
  >
    {{ texto }}
  </button>
</template>

<script>
export default {
  props: {
    paginaPath: {
      type: String,
      default: '/',
    },
    texto: {
      type: String,
      default: '',
    },
    corPrincipal: {
      type: String,
      default: 'white',
    }
  },
  data() {
    return {
      corBotao: {
        color: this.corPrincipal,
        borderColor: this.corPrincipal
      }
    }
  },
  methods: {
    acessarPagina() {
      this.$router.push({ path: this.paginaPath });
    },
  },
};
</script>

<style scoped>
  .custom-button-nuxt-link {
    height: 2.5em;
    font-weight: 600;
    font-size: min(max(0.9rem, 1.5vw), 20px);
    background-color: transparent;
    box-shadow: none;
  }
</style>
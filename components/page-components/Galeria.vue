<template>
  <div class="particao-informacoes-diretoria px-5 py-2">
    <div class="d-md-flex justify-content-between text-center">
      <div
        v-for="(comp, index) in componente.imagens"
        :key="index"
        class="card-coloborador-diretoria"
      >
        <img :src="requestImg(comp.imgUrl)" />
        <h3 class="mt-3" v-html="comp.texto"></h3>
      </div>
    </div>
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
  methods: {
    requestImg(img) {
      if (
        this.SITE_STATICO === false &&
        this.componente.imagens !== undefined
      ) {
        return this.API_URL + "/images/" + img;
      } // else return require("~/assets/imagens/" + this.componente.imgUrl);
    },
  },
};
</script>

<style scoped>
.card-coloborador-diretoria {
  text-align: center;
}

.card-coloborador-diretoria img {
  width: 100%;
}
</style>
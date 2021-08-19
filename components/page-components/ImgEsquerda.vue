<template>
  <div :style="styleFundo()">
    <div
      class="
        conteudo-informacoes-cliente d-md-flex mb-5 px-0 px-md-5
      "
      :style="styleCorTitulo()"
    >
      <div class="w-100">
        <img :src="requestImg()" style="height: 380px;" class="w-100" />
      </div>
      <div class="w-100 text-left p-4 py-md-0 pl-md-5">
        <h2
          class="titulo-companhia"
          :style="styleBorder()"
          v-html="componente.titulo"
        ></h2>
        <p class="pr-5" v-html="componente.texto"></p>
        <CustomButtonNuxtLink
          v-if="componente.txtBotao1 != null && componente.txtBotao1 != ''"
          class="mt-auto w-25"
          :texto="componente.txtBotao1"
          :cor-principal="componente.corBotao1"
          :pagina-path="componente.urlBotao1"
        />
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
    styleFundo() {
      if (this.componente.corFundo !== undefined) {
        return [{ background: this.componente.corFundo }];
      }
    },
    styleCorTitulo() {
      if (this.componente.corTitulo !== undefined) {
        return [{ color: this.componente.corTitulo }];
      }
    },
    styleBorder() {
      if (this.componente.corFundo !== undefined) {
        return [{ "border-bottom": "22px solid " + this.componente.corBotao1 }];
      }
    },
    requestImg() {
      if (
        this.SITE_STATICO === false &&
        this.componente.imagens !== undefined
      ) {
        return this.API_URL + "/images/" + this.componente.imagens[0].imgUrl;
      } // else return require("~/assets/imagens/" + this.componente.imgUrl);
    },
  },
};
</script>

<style scoped>
.particao-identidade-empresa > div {
  width: 50%;
}

.titulo-companhia {
  font-size: min(max(2.2rem, 4vw), 54px);
  font-weight: 700;
}

.particao-identidade-empresa p {
  font-size: 18px;
  padding-right: 1rem;
}
</style>



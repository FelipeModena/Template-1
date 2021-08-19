<template>
  <div class="w-100">
    <div
      v-for="(componente, i) in paginasAPICopia.componente"
      :key="i"
      class="w-100"
    >
     <FormsContato  v-if="componente.tipoComponente=='FORMULARIO E CONTATOS'" :componente="componente"/>
     <FormsMaps  v-if="componente.tipoComponente=='FORMULARIO E IFRAME MAPS'" :componente="componente"/>
     <Cards  v-if="componente.tipoComponente=='CARDS ESTATICOS'" :componente="componente"/>
     <Mapa  v-if="componente.tipoComponente=='MAPA'" :componente="componente"/>
     <ImgPrincipal  v-if="componente.tipoComponente=='BANNER'" :componente="componente"/>
     <TextoCentralizado  v-if="componente.tipoComponente=='TEXTO CENTRALIZADO'" :componente="componente"/>
     <Galeria  v-if="componente.tipoComponente=='MINI GALERIA'" :componente="componente"/>
     <ImgDireita  v-if="componente.tipoComponente=='TEXTO ESQUERDA E IMAGEM DIREITA'" :componente="componente"/>
      <ImgEsquerda  v-if="componente.tipoComponente=='TEXTO DIREITA E IMAGEM ESQUERDA'" :componente="componente"/>
      <BannerPrincipal v-if="componente.tipoComponente=='BANNER PRINCIPAL'" :componente="componente"/>
    </div>
  </div>
</template>

<script>
import { mapActions, mapGetters } from "vuex";
export default {
  data() {
    return {
      paginasAPICopia: "",
    };
  },
    computed: {
      ...mapGetters({
        paginasAPI: "conteudoApi/paginasAPI",
      }),
    },
    watch: {
      paginasAPI () {
        if (process.browser) {
          this.paginasAPI.forEach((pagina) => {
            if (pagina.url === this.$nuxt.$route.path) {
              this.paginasAPICopia = JSON.parse(JSON.stringify(pagina));
            }
          });
        }
      },
    },
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

<style lang="less" scoped>
</style>
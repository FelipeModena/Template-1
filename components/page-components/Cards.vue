<template>
    <div class="particao-clientes p-3 p-md-5 d-flex" :style="styleFundo()">
      <div class="acesso-pagina-clientes w-100 d-flex flex-column justify-content-center align-items-center">
        <h2 v-html="componente.titulo" ></h2>
        <CustomButtonNuxtLink
        v-if="componente.txtBotao1!=null && componente.txtBotao1!=''"
          class="w-50 my-2 my-md-0"
          :texto="componente.txtBotao1"
          :pagina-path="componente.urlBotao1"
        />
      </div>
      <div class="lista-imagens-clientes w-100 container-fluid mt-md-0">
        <div class="row row-cols-2 row-cols-md-3 align-items-center h-100 my-md-0 my-2"> 
          <div
            v-for="img,index in componente.imagens"
            :key="index"
            class="col p-0 px-2 my-2 my-md-0"
          >
            <img
              :src="requestImg(img.imgUrl)"
              class="w-100 bg-white p-4 m-2"
            />
          </div>
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
  methods:{
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
    requestImg(img) {
      if (
        this.SITE_STATICO === false &&
        this.componente.imagens !== undefined
      ) {
        return this.API_URL + "/images/" + img;
      } // else return require("~/assets/imagens/" + this.componente.imgUrl);
    },
  }
};
</script>
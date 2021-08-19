<template>
  <header class="container-header px-4 px-md-5">
    <b-navbar toggleable="md" class="w-100 p-0">
      <div class="conteudo-header">
        <img
          src="~/assets/images/logo-dummy.png"
          class="header-logo img-fluid"
          alt="header logo"
        />

        <b-navbar-toggle target="nav-collapse"> </b-navbar-toggle>
      </div>

      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav class="ml-auto mr-lg-5 mr-md-3">
          <NavHeaderButton
            v-for="(opcao, index) in opcoesHeader()"
            :key="index"
            :texto="opcao.nomePagina"
            :to="opcao.url"
          />
        </b-navbar-nav>

        <b-navbar-nav>
          <div class="particao-rede-social-links">
            <a
              v-for="pagina in linksPaginasRedeSocial"
              :key="pagina.Nome"
              :href="pagina.Url"
              target="_blank"
              class="mx-2 mx-md-1"
            >
              <img :src="require(`~/assets/images/${pagina.Imagem}`)" />
            </a>
          </div>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </header>
</template>

<script>
import { mapGetters } from "vuex";
export default {
  data() {
    return {
      headerPaginas: [
        { nomePagina: "Início", to: "/" },
        { nomePagina: "A Empresa", to: "/empresa" },
        { nomePagina: "Nossos serviços", to: "/servicos" },
        { nomePagina: "Nossos clientes", to: "/clientes" },
        { nomePagina: "Contato", to: "/contato" },
      ],
      linksPaginasRedeSocial: [
        {
          Nome: "Facebook",
          Url: "https://www.facebook.com/sharkdatabr",
          Imagem: "facebook-logo.png",
        },
        {
          Nome: "Instagram",
          Url: "https://www.instagram.com/sharkdata",
          Imagem: "instagram-logo.png",
        },
        {
          Nome: "Linkedin",
          Url: "https://www.linkedin.com/company/sharkdata",
          Imagem: "linkedin-logo.png",
        },
      ],
    };
  },
  computed: {
    ...mapGetters({
      paginasAPI: "conteudoApi/paginasAPI",
    }),
  },

  methods: {
    opcoesHeader() {
      if (this.SITE_STATICO !== false) {
        return this.headerPaginas;
      } else {
        return this.paginasAPI;
      }
    },
  },
};
</script>

<style scoped>
.container-header {
  width: 100%;
  padding: 12px 0;
  margin: 0 auto;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.conteudo-header {
  display: flex;
  justify-content: space-between;
}

img.header-logo {
  width: 12rem;
  height: auto;
  min-width: 7rem;
}

.particao-rede-social-links {
  max-width: 110px;
  display: inline-flex;
  align-self: center;
}
.particao-rede-social-links img {
  filter: invert(100%);
  width: 100%;
  min-width: 1.2rem;
  height: auto;
}

@media (max-width: 768px) {
  .conteudo-header {
    width: 100%;
  }

  .particao-rede-social-links {
    max-width: 130px;
    margin-top: 15px;
  }
}
</style>
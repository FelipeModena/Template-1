<template>
  <footer>
    <div v-if="ativaRodape()" class="container-footer px-4 px-md-5 py-4 mt-5">
      <div class="particao-paginas-site">
        <div class="logo-footer mb-3">
          <img
            src="~/assets/images/logo-dummy-branco.png"
            alt="footer site logo"
            width="160"
          />
        </div>
        <div>
          <NuxtLink
            v-for="(pagina, index) in paginas()"
            :key="index"
            :to="pagina.url"
            >{{ pagina.nomePagina }}</NuxtLink
          >
        </div>
      </div>
      <div class="particao-contatos">
        <div class="d-flex align-items-center">
          <div class="text-white ml-3">
            <p class="m-0">Rua Endereço nº 123</p>
            <p class="m-0">Bairro X</p>
            <p class="m-0">Cidade - Estado</p>
          </div>
        </div>
        <div class="d-flex align-items-center">
          <div class="text-white ml-3">
            <p class="m-0">(11) 1234-5678</p>
          </div>
        </div>
        <div class="d-flex align-items-center">
          <div class="text-white ml-3">
            <p class="m-0">email@email.com.br</p>
          </div>
        </div>
      </div>
      <div v-if="corIcones()" class="particao-links-redes-sociais">
        <a
          v-for="(pagina, index) in iconesContato()"
          :key="index"
          :href="pagina.Url"
          target="_blank"
        >
          <img :src="require(`~/assets/images/${pagina.Imagem}`)" />
        </a>
      </div>
    </div>

    <div
      class="
        container-copyright
        d-flex
        justify-content-between
        align-items-center
        px-4 px-md-5
      "
    >
      <p class="m-0 copyright-text">
        2021 &copy; Nome da empresa todos os direitos reservados
      </p>

      <div class="d-flex align-items-center justify-content-end">
        <p class="m-0 text-nowrap copyright-text">Website by</p>
        <img
          src="~/assets/images/sharkdata-logo.png"
          class="ml-3"
          width="100"
        />
      </div>
    </div>
  </footer>
</template>

<script>
import { mapGetters } from "vuex";
export default {
  data() {
    return {
      footerPaginas: [
        { nomePagina: "Início", url: "/" },
        { nomePagina: "Quem somos", url: "/empresa" },
        { nomePagina: "Nossos serviços", url: "/servicos" },
        { nomePagina: "Cases", url: "/clientes" },
        { nomePagina: "Contato", url: "/contato" },
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
      rodapeAPI: "conteudoApi/rodapeAPI",
      contatoAPI: "conteudoApi/contatoAPI", // usar para site não estatico
      paginasAPI: "conteudoApi/paginasAPI",
    }),
  },
  methods: {
    paginas() {
      if (this.SITE_STATICO === true) {
        return this.footerPaginas;
      } else {
        return this.paginasAPI;
      }
    },
    ativaRodape() {
      if (this.SITE_STATICO === true) {
        return true;
      } else if (this.rodapeAPI != null) {
        return this.rodapeAPI.rodapeAtivo;
      }
    },
    corIcones() {
      if (this.rodapeAPI.iconesRedesSociais === "white") {
        return true;
      } else {
        return false;
      }
    },
    iconesContato() {
      if (this.SITE_STATICO === true) {
        return this.linksPaginasRedeSocial;
      } else {
        return this.linksPaginasRedeSocial
      }
    },
  },
};
</script>

<style scoped>
.container-footer {
  display: flex;
  flex-direction: row;
  height: auto;
  width: 100%;
  background-color: #1e08aa;
}

.particao-paginas-site {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  width: 100%;
  color: white;
}

.particao-paginas-site a {
  display: block;
  color: white;
  font-size: 1.35rem;
}

.particao-contatos {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  width: 100%;
}

.particao-links-redes-sociais {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
}

.particao-links-redes-sociais img {
  width: 3rem;
}

.container-copyright {
  height: 70px;
  color: blue;
  font-weight: 500;
}

@media (max-width: 768px) {
  .container-footer {
    display: block;
    height: auto;
  }

  .particao-contatos {
    margin: 1.5rem 0;
  }
  .particao-contatos > div {
    margin-bottom: 1rem;
  }

  .particao-links-redes-sociais {
    display: block;
  }
  .particao-links-redes-sociais a {
    margin-right: 1rem;
  }

  .particao-links-redes-sociais img {
    width: 2.5rem;
  }

  .copyright-text {
    font-size: 0.8rem;
  }

  .container-copyright > p {
    width: 11rem;
  }

  .container-copyright img {
    width: 4.5rem;
  }
}
</style>
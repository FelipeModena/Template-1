<template>
  <div>
    <div class="particao-banner">
      <img :src="requestImg(componente.imagens[0].imgUrl)" class="w-100" />
      <div class="conteudo-banner" :style="corFundo()">
        <div class="texto-banner">
          <p v-html="componente.titulo"></p>
        </div>
      </div>
    </div>

    <div class="particao-cards-servicos">
      <div class="conteudo-cards px-5">
        <div
          v-for="(img, index) in listaIcones"
          :key="index"
          class="card-servico"
          :style="corFundoCaixasPequenas()"
        >
          <div class="w-100 text-center">
            <img :src="requestImg(img.imgUrl)" class="img-fluid" />
            <h2 class="mt-3" v-html="img.texto"></h2>
          </div>
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
  computed: {
    listaIcones() {
      const lista = [];
      this.componente.imagens.forEach((img, index) => {
        if (index !== 0) {
          lista.push(img);
        }
      });
      return lista;
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
    hexToRgb(hex) {
      const result = /^#?([a-f\d]{2})([a-f\d]{2})([a-f\d]{2})$/i.exec(hex);
      return result
        ? {
            r: parseInt(result[1], 16),
            g: parseInt(result[2], 16),
            b: parseInt(result[3], 16),
          }
        : null;
    },
    corFundo() {
      if (this.SITE_STATICO === false) {
        const coresRgb = this.hexToRgb(this.componente.corFundo);
        return [
          {
            "background-color":
              "rgba(" +
              coresRgb.r +
              "," +
              coresRgb.g +
              "," +
              coresRgb.b +
              "," +
              0.65 +
              ")",
          },
        ];
      }
    },
    corFundoCaixasPequenas() {
      if (this.SITE_STATICO === false) {
        return [{ "background-color": this.componente.corFundo }];
      }
    },
  },
};
</script>

<style scoped>
.particao-banner {
  position: relative;
}

.conteudo-banner {
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);

  width: 60%;
  background-color: rgba(52, 35, 116, 0.65);
}

.texto-banner {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  align-self: center;

  padding: 5% 5%;
  font-size: min(max(1.3rem, 3vw), 2.3rem);
  font-family: Cambria, Cochin, Georgia, Times, "Times New Roman", serif;
  text-align: center;
  color: white;
}
.texto-banner > strong {
  font-size: min(max(2.1rem, 4.4vw), 4.2rem);
}
.texto-banner > p {
  margin-bottom: 0px !important;
  opacity: 0.8;
}

.particao-cards-servicos {
  position: relative;
  width: 100%;
  height: 250px;
}

.conteudo-cards {
  position: absolute;
  bottom: 25%;
  left: 0;
  right: 0;

  width: 100%;
  height: 250px;
  display: flex;
  justify-content: space-between;
}

.card-servico {
  background-color: #1e08aa;
  width: 22%;
  height: auto;
  text-align: center;
  color: white;
  padding: 2%;
  font-size: min(max(0.75rem, 1.5vw), 20px);
}

.card-servico p {
  font-size: min(max(1.25rem, 2vw), 30px);
}

@media (max-width: 768px) {
  .particao-banner img {
    object-fit: cover;
    height: 20rem;
  }

  .conteudo-banner {
    width: 75%;
    height: 65%;
  }

  .texto-banner {
    height: 100%;
    line-height: initial;
    font-size: min(max(1.4rem, 3vw), 1.8rem);
  }
  .texto-banner > strong {
    width: 80%;
    font-size: min(max(1.8rem, 7.5vw), 4rem);
  }
  .texto-banner > p {
    max-width: 18ch;
  }

  .particao-cards-servicos {
    width: 100%;
    height: 100%;
    margin-bottom: 30px;
  }
  .card-servico {
    width: 100%;
    margin: 20px 0;
    padding: 50px 0;
  }

  .conteudo-cards {
    position: static;
    flex-direction: column;
    height: 100%;
  }
}
</style>
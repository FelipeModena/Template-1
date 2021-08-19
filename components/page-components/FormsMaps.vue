<template>
  <div class="particao-contato text-md-center" :style="styleFundo()">
    <h2 class="mx-5 my-3 my-md-4 font-weight-bold display-4">
      {{ componente.titulo }}
    </h2>
    <div class="d-md-flex m-0 mx-md-5">
      <div class="formulario-contato-email w-100 px-5 p-md-0 pr-md-5 mr-md-5">
        <form class="d-flex flex-column text-left">
          <label for="nome">Nome</label>
          <input id="nome" name="nome" type="text" />

          <label for="Telefone">Telefone</label>
          <input id="telefone" name="telefone" type="tel" />

          <label for="">Email</label>
          <input id="email" name="email" type="text" />

          <label for="mensagem">Mensagem</label>
          <textarea id="mensagem" name="mensagem" rows="5"></textarea>
        </form>
        <button class="botao-formulario-contato" :style="syleBtn()">
          Enviar!
        </button>
      </div>
      <div class="mapa-localizacao-empresa w-100 text-center mt-5 mt-md-0">
        <iframe
          src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3690.059624736691!2d-49.052161291819274!3d-22.351377389361936!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x94bf675b498f1c05%3A0x24fea419aba3c6a3!2sBusiness%20Office!5e0!3m2!1spt-BR!2sbr!4v1617906218005!5m2!1spt-BR!2sbr"
          style="border: 0; width: 100%; min-height: 400px; height: 100%"
          allowfullscreen=""
          loading="lazy"
        >
        </iframe>
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
  data() {
    return {
      mobile: false,
    };
  },
  methods: {
    styleFundo() {
      if (this.componente.corFundo !== undefined) {
        return [
          { background: this.componente.corFundo },
          { color: this.componente.corTitulo },
        ];
      }
    },
    syleBtn() {
      return [
        { color: this.componente.corFundo },
        { background: this.componente.corBotao1 },
      ];
    },
    styleCorTitulo() {
      if (this.componente.corTitulo !== undefined) {
        return [{ color: this.componente.corTitulo }];
      }
    },
    requestImg(img) {
      if (
        this.SITE_STATICO === false &&
        this.componente.imagens !== undefined &&
        img !== null &&
        img !== undefined
      ) {
        return this.API_URL + "/images/" + img;
      } // else return require("~/assets/imagens/" + img);
    },
  },
};
</script>

<style  scoped>
.formulario-contato-email label {
  color: #1e08aa;
  font-weight: 500;
  font-size: 18px;
  margin-bottom: 0px;
}

.formulario-contato-email input,
textarea,
input:focus,
textarea:focus {
  border: 2px solid #1e08aa;
  margin-bottom: 15px;
  outline: none;
  resize: none;
}

.formulario-contato-email input#nome,
#telefone,
#email {
  height: 40px;
}

.botao-formulario-contato {
  height: 45px;
  width: 100%;
  background-color: #1e08aa;
  color: white;
  font-size: 20px;
  border: none;
}
</style>
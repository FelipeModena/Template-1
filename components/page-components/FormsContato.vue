<template>

  <div class="particao-pagina-contato">

    <div class="conteudo-informacoes-contato d-flex flex-column-reverse flex-md-row">
      <div class="formulario-contato-email w-100 text-center px-4 px-md-5">
        <h2 class="text-left text-md-center my-3">{{ componente.titulo }}</h2>
        <form class="d-flex flex-column text-left">
          <label for="nome">Nome</label>
          <input id="nome" name="nome" type="text">

          <label for="Telefone">Telefone</label>
          <input id="telefone" name="telefone" type="tel">

          <label for="">Email</label>
          <input id="email" name="email" type="text">

          <label for="mensagem">Mensagem</label>
          <textarea id="mensagem" name="mensagem" rows="5"></textarea>
        </form>
        <button class="botao-formulario-contato" :style="syleBtn()">Enviar!</button>
      </div>
      <div class="dados-contato d-flex flex-column justify-content-between w-100 text-white p-4 p-md-5 my-md-5" :style="styleFundo()">
        <h2>Onde estamos</h2>
        <div class="d-flex align-items-center py-3">
          <img src="~/assets/images/verified.png" width="auto" height="45" />
          <div class="text-white ml-3">
            <p class="m-0">Rua Endereço nº 123</p>
            <p class="m-0">Bairro X</p>
            <p class="m-0">Cidade - Estado</p>
          </div>
        </div>
        <div class="d-flex align-items-center py-3">
          <img src="~/assets/images/verified.png" width="auto" height="45" />
          <div class="text-white ml-3">
            <p class="m-0">(11) 1234-5678</p>
          </div>
        </div>
        <div class="d-flex align-items-center py-3">
          <img src="~/assets/images/verified.png" width="auto" height="45" />
          <div class="text-white ml-3">
            <p class="m-0">email@email.com.br</p>
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
  data() {
    return {
      mobile: false,
    };
  },
  methods: {
    styleFundo() {
      if (this.componente.corFundo !== undefined) {
        return [{ background: this.componente.corFundo },{color:this.componente.corTitulo}];
      }
    },
    syleBtn(){
        return [{color:this.componente.corFundo},{background:this.componente.corBotao1}]
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


<style scoped>
  .conteudo-informacoes-contato h2 {
    font-size: min(max(2.5rem, 2.5vw), 44px);
    font-weight: bold;
  }

  .formulario-contato-email h2 {
    color: #1e08aa;
  }

  .formulario-contato-email label {
    color: #1e08aa;
    font-weight: 500;
    font-size: 18px;
    margin-bottom: 0px;
  }

  .formulario-contato-email 
    input,
    textarea, 
    input:focus, 
    textarea:focus 
  {
    border: 2px solid #1e08aa;
    margin-bottom: 15px;
    outline: none;
    resize: none;
  }

  .formulario-contato-email input#nome, #telefone, #email {
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

  .dados-contato {
    background-color: #1e08aa;
  }
</style>
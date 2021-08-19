<template>
  <div class="container-pagina-inicio">

    <div class="particao-banner">
      <img
        src="~/assets/images/business-people-shaking-hands-together.png"
        class="w-100"
      />
      <div class="conteudo-banner">
        <div class="texto-banner">
          <strong>O crédito que você precisa</strong>
          <p>com liberação rápida e sem burocracia</p>
        </div>
      </div>
    </div>

    <div class="particao-cards-servicos">
      <div class="conteudo-cards px-5">
        <div 
          v-for="servico in servicos"
          :key="servico.Nome"
          class="card-servico"
        >
          <div class="w-100 text-center">
              <img 
                src="~/assets/images/verified.png"
                class="img-fluid"
              />
              <h2 class="mt-3">{{servico.Nome}}</h2>
              <p class="m-auto">{{servico.Descricao}}</p>
          </div>
        </div>
      </div>
    </div>

    <div class="particao-identidade-empresa d-flex flex-column-reverse flex-md-row px-md-5 mb-md-5 mb-3">
      <div class="d-flex flex-column p-3 p-md-0">
        <h2 class="titulo-companhia">A Companhia</h2>
        <p class="pr-5">
          Texto curto apresentando a empresa, sua historia, seus valores, etc.
          Pode ser um botão abaixo que irá levar a página dedicada exclusivamente
          para falar da empresa. Lá é possivel ter mais detalhes, falar dos funcionarios, etc.
          Essa prévia precisa ser sucinta e informativa para quem entrou no site pela primeira vez.
        </p>
        <CustomButtonNuxtLink
          class="mt-auto w-25" 
          texto="Saiba mais"
          cor-principal="#1e08aa"
          pagina-path="/empresa"
        />
      </div>
      <div>
        <img 
          src="~/assets/images/beautiful-architecture-business-office-building-exterior.png"
          class="w-100"
          style="height: 280px; object-fit: cover;"
        />
      </div>
    </div>
    <div class="particao-clientes p-3 p-md-5 d-flex">
      <div class="acesso-pagina-clientes w-100 d-flex flex-column justify-content-center align-items-center">
        <h2>Nossos Clientes</h2>
        <CustomButtonNuxtLink
          class="w-50 my-2 my-md-0"
          texto="Veja todos os cases"
          pagina-path="/clientes"
        />
      </div>
      <div class="lista-imagens-clientes w-100 container-fluid mt-md-0">
        <div class="row row-cols-2 row-cols-md-3 align-items-center h-100 my-md-0 my-2"> 
          <div
            v-for="cliente in numeroListaClientes"
            :key="cliente"
            class="col p-0 px-2 my-2 my-md-0"
          >
            <img
              src="~/assets/images/logo-dummy.png"
              class="w-100 bg-white p-4"
            />
          </div>
        </div>
      </div>
    </div>
    <div class="particao-contato text-md-center">
      <h2 class="mx-5 my-3 my-md-4 font-weight-bold display-4">Fale Conosco</h2>
      <div class="d-md-flex m-0 mx-md-5">
        <div class="formulario-contato-email w-100 px-5 p-md-0 pr-md-5 mr-md-5">
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
          <button class="botao-formulario-contato">Enviar!</button>
        </div>
        <div class="mapa-localizacao-empresa w-100 text-center mt-5 mt-md-0">
          <iframe 
            src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3690.059624736691!2d-49.052161291819274!3d-22.351377389361936!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x94bf675b498f1c05%3A0x24fea419aba3c6a3!2sBusiness%20Office!5e0!3m2!1spt-BR!2sbr!4v1617906218005!5m2!1spt-BR!2sbr"
            style="border:0; width: 100%; min-height: 400px; height: 100%;"
            allowfullscreen=""
            loading="lazy"
          >
          </iframe>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        servicos: [
          {
            Nome: 'Seguros',
            Descricao: 'para todas as situações'
          },
          
          {
            Nome: 'Empréstimos',
            Descricao: 'com liberação fácil e rápida'
          },
          {
            Nome: 'Crédito',
            Descricao: 'para micro e pequenas empresas'
          },
          {
            Nome: 'Financimanto',
            Descricao: 'de veículos e imóveis'
          },
        ],
        numeroListaClientes: 6 
      }
    }
  }
</script>

<style scoped>
  .container-pagina-inicio {
    margin: 0 auto;
    width: 100%;
    height: auto;
  }

  /* PARTIÇÃO DE BANNERS */
  .particao-banner {
    position: relative;
  }

  .conteudo-banner {
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%,-50%);

    width: 60%;
    background-color: rgba(52, 35, 116, .65);
  }

  .texto-banner {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    align-self: center;

    padding: 5% 5%;
    font-size: min(max(1.3rem, 3vw), 2.3rem);
    font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
    text-align: center;
    color: white;
  }
    .texto-banner > strong {
      font-size: min(max(2.1rem, 4.4vw), 4.2rem);
    }
    .texto-banner > p {
      margin-bottom: 0px !important;
      opacity: .8;
    }

  /* PARTIÇÃO DE SERVIÇOS */
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
    font-size: min(max(.75rem, 1.5vw), 20px);
  }

  .card-servico h2 {
    font-size: min(max(1.25rem, 2vw), 30px);
  }

  /* PARTIÇÃO DA COMPANHIA / EMPRESA */
  .particao-identidade-empresa > div {
    width: 50%;
  }

  .titulo-companhia {
    font-size: min(max(2.2rem, 4vw), 54px);
    font-weight: 700;
    border-bottom: 22px solid #1e08aa;
  }

  .particao-identidade-empresa p {
    font-size: 18px;
    padding-right: 1rem;
  }

  /* PARTIÇÃO DE CLIENTES */
  .particao-clientes {
    width: 100%;
    color: white;
    background-color: #1e08aa;
    text-align: center;
    min-height: 330px;
    justify-content: center;
  }

  .acesso-pagina-clientes > h2 {
    font-weight: 700;
    font-size: min(max(2.3rem, 5vw), 5rem);
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

  @media (max-width: 768px) {
    .particao-banner img {
      object-fit:cover;
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

    .conteudo-cards {
      position: static;
      flex-direction: column;
      height: 100%;
    }

    .card-servico {
      width: 100%;
      margin: 20px 0;
      padding: 50px 0;
    }

    .particao-identidade-empresa > div {
      width: 100%;
    }

    .titulo-companhia {
      border-bottom: none;
    }

    .particao-clientes {
      flex-direction: column;
    }

    .particao-clientes > div {
      width: 100%;
    }
  }
</style>

<template>
  <div class="particao-pagina-contato">
    <div class="mapa-localizacao-empresa w-100 mb-3">
      <iframe 
        src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3690.059624736691!2d-49.052161291819274!3d-22.351377389361936!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x94bf675b498f1c05%3A0x24fea419aba3c6a3!2sBusiness%20Office!5e0!3m2!1spt-BR!2sbr!4v1617906218005!5m2!1spt-BR!2sbr"
        style="border:0; width: 100%; min-height: 400px; height: 100%;"
        allowfullscreen=""
        loading="lazy"
      >
      </iframe>
    </div>
    <div class="conteudo-informacoes-contato d-flex flex-column-reverse flex-md-row">
      <div class="formulario-contato-email w-100 text-center px-4 px-md-5">
        <h2 class="text-left text-md-center my-3">Fale Conosco</h2>
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
      <div class="dados-contato d-flex flex-column justify-content-between w-100 text-white p-4 p-md-5 my-md-5">
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
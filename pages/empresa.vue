<template>
  <div class="container-pagina-empresa">
    <div class="particao-informacoes-empresa">
      <img 
        src="~/assets/images/beautiful-architecture-business-office-building-exterior.png"
        class="w-100"
      />
      <div class="w-100 p-3 p-md-5 text-center">
        <h2>A Companhia</h2>
        <p class="w-100 py-2 text-left">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit,
          sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
          Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
          Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
          Excepteur sint occaecat cupidatat non proident,
          sunt in culpa qui officia deserunt mollit anim id est laborum.
        </p>
      </div>
    </div>
    <div class="particao-informacoes-equipe">
      <img 
        src="~/assets/images/businessman-business-women-front-building.png"
        class="w-100"
      />
      <div class="w-100 p-3 p-md-5 text-center">
        <h2>Nossa Equipe</h2>
        <p class="w-100 py-2 text-left">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit,
          sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
          Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
          Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
          Excepteur sint occaecat cupidatat non proident,
          sunt in culpa qui officia deserunt mollit anim id est laborum.
        </p>
      </div>
    </div>
    <div class="particao-informacoes-diretoria px-5 py-2">
      <div class="d-md-flex justify-content-between">
        <div class="card-coloborador-diretoria">
          <img 
            src="~/assets/images/cheerful-middle-aged-woman-with-curly-hair.png"
          />
          <h3 class="mt-3">Maria Ferreira</h3>
          <p>Co-fundadora</p>
        </div>
        <div class="card-coloborador-diretoria">
          <img 
            src="~/assets/images/medium-shot-senior-man-with-crossed-arms.png"
          />
          <h3 class="mt-3">José Penteado</h3>
          <p>Co-fundador</p>
        </div>
        <div class="card-coloborador-diretoria">
          <img 
            src="~/assets/images/confident-young-businessman-suit-standing-with-arms-folded.png"
          />
          <h3 class="mt-3">Armando Torres</h3>
          <p>Diretor geral</p>
        </div>
        <div class="card-coloborador-diretoria">
          <img 
            src="~/assets/images/portrait-charming-attractive-young-african-american-female-with-voluminous-afro-haircut-with-broad-confident-smile-keeping-her-arms-folded-chest-wearing-striped-nightgown.png"
          />
          <h3 class="mt-3">Juliana Rosa</h3>
          <p>Gerente de contas</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {}
</script>
  
<style scoped>
  .container-pagina-empresa h3 {
    font-size: min(max(2.3rem, 4vw), 28px);
    font-weight: bold;
  }

  .container-pagina-empresa p {
    font-size: min(max(2rem, 3vw), 20px);
    padding: 0 20%;
  }

  .card-coloborador-diretoria {
    text-align: center;
  }

  .card-coloborador-diretoria img {
    width: 100%;
  }

  @media (max-width: 768px) { 
    .container-pagina-empresa p {
      padding: 0 5%;
    }
  }
</style>

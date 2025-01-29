<script>
  const projetos = [
      {
          titulo: "Head of a skeleton with a burning cigarette",
          imagem: "https://upload.wikimedia.org/wikipedia/commons/thumb/8/87/Vincent_van_Gogh_-_Head_of_a_skeleton_with_a_burning_cigarette_-_Google_Art_Project.jpg/772px-Vincent_van_Gogh_-_Head_of_a_skeleton_with_a_burning_cigarette_-_Google_Art_Project.jpg",
          descricao: "Uma pintura que expressa uma abordagem única sobre a morte e a vida através do esqueleto."
      },
      {
          titulo: "Two Rats",
          imagem: "https://upload.wikimedia.org/wikipedia/commons/b/ba/Van_gogh-two_rats-f177.jpg",
          descricao: "Obra que representa a simplicidade e o olhar agudo do pintor para a natureza."
      },
      {
          titulo: "Café Terrace at Night",
          imagem: "https://upload.wikimedia.org/wikipedia/commons/0/0c/Vincent_Willem_van_Gogh_-_Cafe_Terrace_at_Night_%28Yorck%29.jpg",
          descricao: "Uma das obras mais famosas de Van Gogh, retratando uma noite iluminada em Arles."
      }
  ];

  window.onload = () => {
    const galeria = document.querySelector('.galeria');

    projetos.forEach(projeto => {
      const divProjeto = document.createElement('div');
      divProjeto.classList.add('projeto');

      const imagem = document.createElement('img');
      imagem.src = projeto.imagem;
      imagem.alt = projeto.titulo;

      const titulo = document.createElement('h3');
      titulo.textContent = projeto.titulo;

      const descricao = document.createElement('p');
      descricao.textContent = projeto.descricao;

      divProjeto.appendChild(imagem);
      divProjeto.appendChild(titulo);
      divProjeto.appendChild(descricao);

      galeria.appendChild(divProjeto);
    });
  };
</script>

<main>
  <header>
      <div class="gif-container">
          <div class="tenor-gif-embed" data-postid="18138571" data-share-method="host" data-aspect-ratio="1.60804" data-width="100%">
              <a href="https://tenor.com/view/noite-estrelada-gif-18138571">Noite Estrelada GIF</a> from <a href="https://tenor.com/search/noite+estrelada-gifs">Noite Estrelada GIFs</a>
          </div>
          <script type="text/javascript" async src="https://tenor.com/embed.js"></script>
      </div>
      <div class="titulo-faixa">
          <h1>Obras de Vincent van Gogh</h1>
      </div>
  </header>

  <section class="galeria">
    <!-- Os projetos serão gerados aqui com JavaScript -->
  </section>

  <footer>
      <p>por Rayssa Monteiro</p>
  </footer>
</main>

<style>
  main {
      font-family: 'Arial', sans-serif;
      margin: 0;
      padding: 0;
      background-color: #f4f4f9;
  }

  header {
      text-align: center;
      position: relative;
      width: 100%;
      height: 100vh;
  }

  .gif-container {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      overflow: hidden;
  }

  .tenor-gif-embed {
      width: 100%;
      height: 100%;
  }

  .titulo-faixa {
      background-color: #52595f; /* Cor do rodapé */
      padding: 20px 0;
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      width: 80%;
      border-radius: 8px;
  }

  h1 {
      color: white;
      font-size: 2.5em;
      margin: 0;
  }

  .galeria {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      padding: 20px;
  }

  .projeto {
      margin: 15px;
      width: 280px;
      border: 1px solid #ddd;
      border-radius: 8px;
      overflow: hidden;
      background-color: white;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
      text-align: center;
      transition: transform 0.3s ease, box-shadow 0.3s ease;
  }

  .projeto:hover {
      transform: translateY(-5px);
      box-shadow: 0 8px 20px rgba(0, 0, 0, 0.2);
  }

  .projeto img {
      width: 100%;
      height: auto;
      border-bottom: 1px solid #ddd;
  }

  .projeto h3 {
      margin: 15px 0;
      font-size: 1.2em;
      color: #333;
  }

  .projeto p {
      padding: 0 10px 15px;
      color: #555;
      font-size: 1em;
  }

  footer {
      text-align: center;
      padding: 20px;
      background-color: #52595f;
      color: white;
      margin-top: 40px;
      width: 100%;
  }
</style>

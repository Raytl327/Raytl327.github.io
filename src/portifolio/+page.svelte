<script>
    const projetos = [
      {
        titulo: "Projeto 1",
        descricao: "Descrição do projeto 1",
        imagem: "/imagens/projeto1.jpg"
      },
      {
        titulo: "Projeto 2",
        descricao: "Descrição do projeto 2",
        imagem: "/imagens/projeto2.jpg"
      },
      {
        titulo: "Projeto 3",
        descricao: "Descrição do projeto 3",
        imagem: "/imagens/projeto3.jpg"
      }
    ];
  </script>
  
  <main>
    <header>
      <h1>Meu Portfólio</h1>
      <p>Bem-vindo ao meu portfólio. Aqui você encontra meus projetos mais recentes.</p>
    </header>
  
    <section class="galeria">
      {#each projetos as { titulo, descricao, imagem }}
        <div class="projeto">
          <img src={imagem} alt={titulo} />
          <h3>{titulo}</h3>
          <p>{descricao}</p>
        </div>
      {/each}
    </section>
  
    <footer>
      <p>Feito com ❤️ usando Svelte.</p>
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
      padding: 20px;
      background-color: #333;
      color: white;
    }
  
    h1 {
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
      width: 250px;
      border: 1px solid #ddd;
      border-radius: 8px;
      overflow: hidden;
      background-color: white;
      box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
      text-align: center;
    }
  
    .projeto img {
      width: 100%;
      height: auto;
      border-bottom: 1px solid #ddd;
    }
  
    .projeto h3 {
      margin: 15px 0;
      font-size: 1.2em;
    }
  
    .projeto p {
      padding: 0 10px 15px;
      color: #555;
    }
  
    footer {
      text-align: center;
      padding: 20px;
      background-color: #333;
      color: white;
      position: absolute;
      bottom: 0;
      width: 100%;
    }
  </style>
  
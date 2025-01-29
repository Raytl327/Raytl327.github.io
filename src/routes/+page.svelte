<script>
	const projetos = [
		{
			titulo: 'Caveira com Cigarro Aceso',
			imagem: 'skull.jpg',
			url: 'https://app.smartify.org/pt-BR/objects/vincent-van-gogh-skull-of-a-skeleton-with-burning-cigarette'
		},
		{
			titulo: 'Autorretrato com Chapéu de Palha',
			imagem: 'gogh.jpg',
            url: 'https://pt.wikipedia.org/wiki/Autorretrato_com_Chap%C3%A9u_de_Feltro_Cinza'
		},
		{
			titulo: 'Terraço do Café na Praça do Fórum',
			imagem: 'cafe.jpg',
            url: 'https://app.smartify.org/pt-BR/objects/vincent-van-gogh-cafe-terrace-at-night'
		},
		{
			titulo: 'Os Girassóis',
			imagem: 'girassol.jpg',
            url: 'https://ceugaleria.com.br/o-simbolismo-e-a-beleza-de-os-girassois-de-vincent-van-gogh/#:~:text=%E2%80%9COs%20Girass%C3%B3is%E2%80%9D%20%C3%A9%20uma%20das,da%20natureza%20e%20da%20vida.'
		},
		{
			titulo: 'Amendoeira em Flor',
			imagem: 'flor.jpg',
            url: 'https://artrianon.com/2018/03/29/obra-de-arte-da-semana-amendoeira-em-flor-de-vincent-van-gogh/'
		}
	];
</script>

<main>
	<header>
		<div class="gif-container">
			<div
				class="tenor-gif-embed"
				data-postid="18138571"
				data-share-method="host"
				data-aspect-ratio="1.60804"
				data-width="100%"
			>
				<a href="https://tenor.com/view/noite-estrelada-gif-18138571">Noite Estrelada GIF</a> from
				<a href="https://tenor.com/search/noite+estrelada-gifs">Noite Estrelada GIFs</a>
			</div>
			<script type="text/javascript" async src="https://tenor.com/embed.js"></script>
		</div>
		<h1>Memórias de Vincent Van Gogh</h1>
		<p></p>
	</header>

	<section class="galeria">
		{#each projetos as { titulo, descricao, imagem, url }}
			<div class="projeto"> 
                <a href="{url}" style="text-decoration: none;" target="_blank"> 
				<img src={imagem} alt={titulo} />
				<h3>{titulo}</h3>
				<p>{descricao}</p>
            </a>
			</div>
		{/each}
	</section>

	<footer>
		<p>por Rayssa Monteiro</p>
		<p>@ifms.tl</p>
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

	h1 {
		position: absolute;
		top: 50%;
		left: 50%;
		transform: translate(-50%, -50%);
		color: white;
		background: rgba(0, 0, 0, 0.5);
		padding: 10px;
		border-radius: 5px;
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
		background-color: #52595f;
		color: white;
		margin-top: 40px;
		width: 100%;
	}
</style>

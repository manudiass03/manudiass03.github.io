<script>
    import { onMount } from 'svelte';
    let page = 'home';
    let colors = [
        { name: 'Branco', fact: 'Gatos brancos podem ter olhos azuis, mas muitos são surdos devido a um gene ligado à cor. Além disso, sua pelagem reflete a luz do sol, tornando-os mais suscetíveis a queimaduras solares.', color: '#E0E0E0', textColor: 'black', image: 'branco.jpg' },
        { name: 'Preto', fact: 'Gatos pretos são considerados símbolo de sorte em alguns países. São conhecidos por sua resistência e elegância, além de serem menos propensos a doenças genéticas.', color: '#000000', textColor: 'white', image: 'preto.jpg' },
        { name: 'Cinza', fact: 'O gato cinza russo é conhecido por sua pelagem macia e personalidade afetuosa. Eles costumam ser brincalhões e leais aos seus donos.', color: '#808080', textColor: 'white', image: 'cinza.jpg' },
        { name: 'Laranja', fact: 'Gatos laranjas costumam ser machos devido a um gene ligado ao cromossomo X. Eles têm uma personalidade extrovertida e costumam ser muito sociáveis.', color: '#FFA500', textColor: 'white', image: 'laranja.jpg' },
        { name: 'Siamês', fact: 'Os siameses nascem brancos e desenvolvem suas cores à medida que crescem. São muito vocais e adoram interagir com seus donos.', color: '#D2B48C', textColor: 'white', image: 'siames.jpg' },
        { name: 'Rajado', fact: 'O padrão rajado é o mais comum entre gatos, presente em diversas raças. Eles são ágeis, espertos e ótimos caçadores.', color: '#D2691E', textColor: 'white', image: 'rajado.jpg' },
        { name: 'Calico', fact: 'Gatos calicos são quase sempre fêmeas devido à combinação genética das cores. Sua pelagem única os torna muito desejados por amantes de gatos.', color: '#FFCC00', textColor: 'black', image: 'calico.jpg' },
        { name: 'Chocolate', fact: 'Gatos chocolate são raros e geralmente pertencem à raça Havana Brown. São conhecidos por sua personalidade afetuosa e lealdade.', color: '#5C3317', textColor: 'white', image: 'chocolate.jpg' },
        { name: 'Frajola', fact: 'Os gatos Frajola possuem a clássica coloração preta e branca e são conhecidos por serem brincalhões e amigáveis. Seu padrão de cores é popular em diversas raças.', color: '#000000', textColor: 'white', image: 'frajola.jpg' }
    ];
</script>

<style>
    body {
        font-family: Arial, sans-serif;
        text-align: center;
        margin: 0;
        padding: 0;
        background: #f8f9fa;
    }
    nav {
        background: #555;
        color: white;
        padding: 15px;
        display: flex;
        justify-content: center;
        gap: 20px;
        border-radius: 10px;
        margin: 10px;
    }
    nav button {
        background: none;
        border: none;
        color: white;
        font-size: 18px;
        cursor: pointer;
    }
    .gallery {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        gap: 20px;
        padding: 20px;
    }
    .card {
        padding: 20px;
        border-radius: 10px;
        font-weight: bold;
        min-height: 250px;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        transition: transform 0.3s ease, box-shadow 0.3s ease;
    }
    .card:hover {
        transform: scale(1.1);
        box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
    }
    .card img {
        width: 130px;
        height: 130px;
        border-radius: 50%;
        object-fit: cover;
        margin-bottom: 10px;
    }
    .container {
        padding: 20px;
    }
    h1 {
        text-align: center;
    }
    footer {
        background: #333;
        color: white;
        padding: 15px;
        text-align: center;
        margin-top: 20px;
    }
    .adoption-benefits {
        background: #f0f0f0;
        padding: 20px;
        margin: 20px auto;
        border-radius: 10px;
        max-width: 800px;
    }
</style>

<nav>
    <button on:click={() => page = 'home'}>Home</button>
    <button on:click={() => page = 'contato'}>Contato</button>
</nav>

{#if page === 'home'}
    <div class="container">
        <h1>Galeria de Cores de Gatos</h1>
        <div class="gallery">
            {#each colors as cat}
                <div class="card" style="background: {cat.color}; color: {cat.textColor}">
                    <img src={cat.image} alt={cat.name}>
                    <p>{cat.name}</p>
                    <small>{cat.fact}</small>
                </div>
            {/each}
        </div>
        <div class="adoption-benefits">
            <h2>Benefícios de Adotar um Gato🐈</h2>
            <p>Adotar um gato pode trazer inúmeros benefícios para sua vida. Eles são ótimos companheiros, ajudam a reduzir o estresse e a ansiedade, além de exigirem menos manutenção do que outros pets. Gatos também são independentes, mas adoram carinho e podem criar laços profundos com seus donos. Ao adotar, você também está salvando uma vida e contribuindo para o bem-estar dos animais abandonados.</p>
        </div>
    </div>
{:else if page === 'contato'}
    <div class="container">
        <h1>Contato</h1>
        <p>Quer saber mais sobre gatos? Entre em contato pelo email: <b>emanuelle.dias@estudante.ifms.edu.br</b></p>
    </div>
{/if}
</div>
        <div class="big-card">
            <h2>Conheça o Laranjo</h2>
            <img src="laranjo.jpg" alt="Laranjo">
            <p>O Laranjo é um gato muito gordinho e tem cerca de 9 meses. Ele adora sachê, subir na mesa e brincar com bolinhas de papel!</p>
        </div>
    </div>


<footer>
    <p>Feito por Emanuelle Dias - Informática 4B</p>
    <p>Email: <b>emanuelle.dias@estudante.ifms.edu.br</b></p>
</footer>

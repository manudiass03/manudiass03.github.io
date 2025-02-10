<script>
    import { onMount } from 'svelte';
    let page = 'home';
    let colors = [
        { name: 'Branco', fact: 'Gatos brancos podem ter olhos azuis, mas muitos são surdos devido a um gene ligado à cor.', color: '#ffffff', image: 'branco.jpg' },
        { name: 'Preto', fact: 'Gatos pretos são considerados símbolo de sorte em alguns países.', color: '#000000', image: 'preto.jpg' },
        { name: 'Cinza', fact: 'O gato cinza russo é conhecido por sua pelagem macia e personalidade afetuosa.', color: '#808080', image: 'cinza.jpg' },
        { name: 'Laranja', fact: 'Gatos laranjas costumam ser machos devido a um gene ligado ao cromossomo X.', color: '#FFA500', image: 'laranja.jpg' },
        { name: 'Siamês', fact: 'Os siameses nascem brancos e desenvolvem suas cores à medida que crescem.', color: '#F5DEB3', image: 'siames.jpg' },
        { name: 'Rajado', fact: 'O padrão rajado é o mais comum entre gatos, presente em diversas raças.', color: '#D2691E', image: 'rajado.jpg' },
        { name: 'Calico', fact: 'Gatos calicos são quase sempre fêmeas devido à combinação genética das cores.', color: '#FFCC00', image: 'calico.jpg' },
        { name: 'Chocolate', fact: 'Gatos chocolate são raros e geralmente pertencem à raça Havana Brown.', color: '#5C3317', image: 'chocolate.jpg' },
        { name: 'Frajola', fact: 'Os gatos Frajola possuem a clássica coloração preta e branca e são conhecidos por serem brincalhões.', color: '#000000', image: 'frajola.jpg' }
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
        background: #333;
        color: white;
        padding: 15px;
        display: flex;
        justify-content: center;
        gap: 20px;
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
        grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
        gap: 20px;
        padding: 20px;
    }
    .card {
        padding: 15px;
        border-radius: 10px;
        color: white;
        font-weight: bold;
        min-height: 180px;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }
    .card img {
        width: 100px;
        height: 100px;
        border-radius: 50%;
        object-fit: cover;
        margin-bottom: 10px;
    }
    .container {
        padding: 20px;
    }
</style>

<nav>
    <button on:click={() => page = 'home'}>Home</button>
    <button on:click={() => page = 'sobre'}>Sobre</button>
    <button on:click={() => page = 'contato'}>Contato</button>
</nav>

{#if page === 'home'}
    <div class="container">
        <h1>Galeria de Cores de Gatos</h1>
        <div class="gallery">
            {#each colors as cat}
                <div class="card" style="background: {cat.color}">
                    <img src={cat.image} alt={cat.name}>
                    <p>{cat.name}</p>
                    <small>{cat.fact}</small>
                </div>
            {/each}
        </div>
    </div>
{:else if page === 'sobre'}
    <div class="container">
        <h1>Sobre os Gatos</h1>
        <p>Os gatos são animais fascinantes e cheios de curiosidades. Desde suas habilidades de comunicação até suas cores variadas, há muito para aprender sobre eles.</p>
    </div>
{:else if page === 'contato'}
    <div class="container">
        <h1>Contato</h1>
        <p>Quer saber mais sobre gatos? Entre em contato pelo email: <b>contato@gatolover.com</b></p>
    </div>
{/if}

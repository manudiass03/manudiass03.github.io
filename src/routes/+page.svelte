<script>
  let corSelecionada = 'preto';

  const curiosidades = {
    preto: {
      titulo: 'Gato Preto',
      imagem: '/assets/images/gato-preto.jpg',
      descricao: 'Os gatos pretos têm uma longa história repleta de mitos e crenças populares, sendo frequentemente associados a superstições. A cor preta é causada pela presença de um gene recessivo, que resulta em uma pelagem completamente escura.',
      curiosidades: [
        "Os gatos pretos são frequentemente vistos em superstições, principalmente em países ocidentais, onde acredita-se que eles trazem boa ou má sorte.",
        "No entanto, em algumas culturas, como na Egito Antigo, os gatos pretos eram vistos como símbolos de boa sorte e proteção.",
        "A cor preta também é associada à genética recessiva, o que significa que para um gato nascer preto, ambos os pais precisam carregar o gene da pelagem escura.",
        "Gatos pretos têm a mesma personalidade que outras cores, mas por conta da superstição, muitas vezes são mais difíceis de serem adotados."
      ]
    },
    branco: {
      titulo: 'Gato Branco',
      imagem: '/assets/images/gato-branco.jpg',
      descricao: 'Os gatos brancos têm uma aparência radiante e impressionante. A pelagem branca é uma mutação genética que afeta a distribuição de pigmentos no pelo, resultando em uma pelagem completamente branca.',
      curiosidades: [
        "Gatos brancos têm uma maior tendência à surdez, uma característica comum devido à mutação genética que também causa a pelagem branca.",
        "Além da surdez, alguns gatos brancos podem também ser mais sensíveis à luz solar e, por isso, precisam de cuidados extras com a exposição ao sol.",
        "Embora muitos gatos brancos sejam extremamente adoráveis e populares, eles podem exigir cuidados específicos, como visitas regulares ao veterinário."
      ]
    },
    cinza: {
      titulo: 'Gato Cinza',
      imagem: '/assets/images/gato-cinza.jpg',
      descricao: 'Os gatos cinzas possuem uma pelagem elegante e são muitas vezes confundidos com gatos de pelagem azul. A cor cinza pode variar de tons mais claros até o cinza escuro, e é resultado da combinação de genes específicos.',
      curiosidades: [
        "Gatos cinzas podem ter pelagens que variam do cinza claro até o cinza escuro, e essa cor é muitas vezes chamada de 'azul' em algumas raças.",
        "Eles são conhecidos por serem mais calmos e equilibrados em sua personalidade, embora isso dependa de cada gato individualmente.",
        "A cor cinza é particularmente comum em raças como o Chartreux e o Russian Blue, que são conhecidos por suas pelagens densas e macias."
      ]
    }
  };

  function changeCor(cor) {
    corSelecionada = cor;
  }
</script>

<style>
  main {
    font-family: 'Arial', sans-serif;
    background-color: #f4f4f9;
    color: #333;
    padding: 30px;
  }

  h1 {
    text-align: center;
    color: #555;
    font-size: 2.5em;
  }

  .gato-info {
    display: flex;
    flex-direction: column;
    align-items: center;
    background: white;
    border-radius: 10px;
    padding: 20px;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
    margin: 20px 0;
  }

  .gato-info img {
    max-width: 300px;
    border-radius: 10px;
    margin-bottom: 20px;
  }

  .gato-info h2 {
    font-size: 2em;
    color: #2c3e50;
  }

  .gato-info p {
    font-size: 1.1em;
    line-height: 1.6;
    color: #444;
  }

  .gato-info ul {
    list-style-type: none;
    padding: 0;
  }

  .gato-info ul li {
    margin: 10px 0;
    font-size: 1.1em;
  }

  .menu-cor {
    display: flex;
    justify-content: center;
    gap: 20px;
    margin-bottom: 20px;
  }

  .menu-cor button {
    padding: 10px 20px;
    font-size: 1.2em;
    cursor: pointer;
    background-color: #3498db;
    color: white;
    border: none;
    border-radius: 5px;
    transition: background-color 0.3s;
  }

  .menu-cor button:hover {
    background-color: #2980b9;
  }

  .footer {
    text-align: center;
    margin-top: 40px;
    font-size: 0.9em;
    color: #777;
  }
</style>

<main>
  <h1>Curiosidades sobre a Cor dos Gatos</h1>

  <div class="menu-cor">
    <button on:click={() => changeCor('preto')}>Preto</button>
    <button on:click={() => changeCor('branco')}>Branco</button>
    <button on:click={() => changeCor('cinza')}>Cinza</button>
  </div>

  <div class="gato-info">
    <img src={curiosidades[corSelecionada].imagem} alt={curiosidades[corSelecionada].titulo} />
    <h2>{curiosidades[corSelecionada].titulo}</h2>
    <p>{curiosidades[corSelecionada].descricao}</p>
    <ul>
      {#each curiosidades[corSelecionada].curiosidades as curiosidade}
        <li>{curiosidade}</li>
      {/each}
    </ul>
  </div>

  <div class="footer">
    <p>Feito com 💻 por [Seu Nome]. <br /> © 2025 Todos os direitos reservados.</p>
  </div>
</main>

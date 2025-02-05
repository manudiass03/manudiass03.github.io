<script>
  const catColors = [
    { name: "Preto", image: "https://placekitten.com/300/200", description: "Gatos pretos são elegantes e misteriosos, muitas vezes associados a superstições." },
    { name: "Branco", image: "https://placekitten.com/301/200", description: "Gatos brancos são puros e delicados, frequentemente ligados à paz e tranquilidade." },
    { name: "Cinza", image: "https://placekitten.com/302/200", description: "Gatos cinza são sofisticados e muitas vezes têm um comportamento calmo e sereno." },
    { name: "Laranja", image: "https://placekitten.com/303/200", description: "Gatos laranja são energéticos e brincalhões, conhecidos por sua personalidade forte." },
    { name: "Siamês", image: "https://placekitten.com/304/200", description: "Os gatos siameses são muito comunicativos e leais aos seus donos." },
    { name: "Tigrado", image: "https://placekitten.com/305/200", description: "Gatos tigrados possuem um padrão listrado e são extremamente ágeis." },
    { name: "Bicolor", image: "https://placekitten.com/306/200", description: "Gatos bicolores têm uma bela mistura de duas cores distintas no pelo." },
    { name: "Tricolor", image: "https://placekitten.com/307/200", description: "Gatos tricolores são quase sempre fêmeas e possuem uma pelagem única e vibrante." },
    { name: "Chocolate", image: "https://placekitten.com/308/200", description: "Gatos chocolate têm um tom marrom profundo e são muito raros." },
    { name: "Lilás", image: "https://placekitten.com/309/200", description: "Gatos lilás têm uma cor suave e encantadora, sendo uma variação rara do cinza." }
  ];
</script>

<style>
  .container {
    @apply max-w-4xl mx-auto p-6;
  }
  .grid {
    @apply grid grid-cols-2 md:grid-cols-3 gap-4;
  }
  .card {
    @apply bg-white shadow-lg rounded-lg overflow-hidden;
  }
  .card img {
    @apply w-full h-40 object-cover;
  }
  .card h3 {
    @apply text-lg font-bold text-center p-2;
  }
  .card p {
    @apply text-sm text-center p-2;
  }
  .footer {
    @apply text-center mt-6 p-4 bg-gray-200;
  }
</style>

<main class="container">
  <h1 class="text-3xl font-bold text-center mb-6">Cores de Gatos</h1>
  <div class="grid">
    {#each catColors as cat}
      <div class="card">
        <img src={cat.image} alt={cat.name} />
        <h3>{cat.name}</h3>
        <p>{cat.description}</p>
      </div>
    {/each}
  </div>
</main>

<footer class="footer">
  <p>Desenvolvido por [Seu Nome] - Série [Sua Série]</p>
</footer>
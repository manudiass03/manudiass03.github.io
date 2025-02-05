+layout.svelte:
<script>
  import { onMount } from 'svelte';
</script>

<nav class="p-4 bg-gray-800 text-white flex justify-center space-x-4">
  <a href="/" class="hover:underline">Início</a>
  <a href="/sobre" class="hover:underline">Sobre</a>
  <a href="/contato" class="hover:underline">Contato</a>
</nav>

<slot />

<footer class="footer text-center mt-6 p-4 bg-gray-200">
  <p>Desenvolvido por [Seu Nome] - Série [Sua Série]</p>
</footer>

+page.svelte:
<script>
  import { onMount } from 'svelte';
  const catColors = [
    { name: "Preto", image: "https://placekitten.com/300/200", description: "Gatos pretos são misteriosos e elegantes." },
    { name: "Branco", image: "https://placekitten.com/301/200", description: "Gatos brancos simbolizam paz e pureza." },
    { name: "Cinza", image: "https://placekitten.com/302/200", description: "Gatos cinza são sofisticados e reservados." },
    { name: "Laranja", image: "https://placekitten.com/303/200", description: "Gatos laranja são brincalhões e carismáticos." },
    { name: "Siamês", image: "https://placekitten.com/304/200", description: "Siameses são falantes e muito apegados aos donos." },
    { name: "Tigrado", image: "https://placekitten.com/305/200", description: "Gatos tigrados têm um padrão único e são ágeis." },
    { name: "Bicolor", image: "https://placekitten.com/306/200", description: "Bicolores possuem lindas combinações de cores." },
    { name: "Tricolor", image: "https://placekitten.com/307/200", description: "Tricolores são quase sempre fêmeas." },
    { name: "Chocolate", image: "https://placekitten.com/308/200", description: "Gatos chocolate são raros e muito cobiçados." },
    { name: "Lilás", image: "https://placekitten.com/309/200", description: "Lilás é uma tonalidade suave e encantadora." }
  ];
</script>

<main class="container mx-auto p-6">
  <h1 class="text-3xl font-bold text-center mb-6">Cores de Gatos</h1>
  <div class="grid grid-cols-2 md:grid-cols-3 gap-4">
    {#each catColors as cat}
      <div class="card bg-white shadow-lg rounded-lg overflow-hidden">
        <img src={cat.image} alt={cat.name} class="w-full h-40 object-cover" />
        <h3 class="text-lg font-bold text-center p-2">{cat.name}</h3>
        <p class="text-sm text-center p-2">{cat.description}</p>
      </div>
    {/each}
  </div>
</main>

+page.svelte (Sobre):
<h1 class="text-3xl font-bold text-center mt-6">Sobre o Site</h1>
<p class="text-center mt-4">Este site foi criado para mostrar diferentes cores de gatos e suas características.</p>

+page.svelte (Contato):
<h1 class="text-3xl font-bold text-center mt-6">Contato</h1>
<p class="text-center mt-4">Para mais informações, envie um e-mail para contato@exemplo.com.</p>

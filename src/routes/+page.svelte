<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://svelte.dev/docs/kit">svelte.dev/docs/kit</a> to read the documentation</p>
<script>
    import { recipes } from '$lib/recipes';
  </script>
  
  <style>

    .recipe-card {
      border-radius: 8px;
      margin-bottom: 20px;
    }
  
    .recipe-card img {
      border-radius: 8px;
    }
  </style>
  

  <head>
    <link
      rel="stylesheet"
      href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/css/bootstrap.min.css"
      integrity="sha384-GLhlTQ8iRABmZ1M2U7U5oI5t7BEx3eJ8dL56V9evH2WbRo4s5F5p5oF4vYh4B5dr"
      crossorigin="anonymous"
    />
  </head>
  
  <main class="container py-4">
    <h1 class="text-center mb-5">Blog de Receitas Culinárias</h1>
  
    <div class="row">
      {#each recipes as recipe}
        <div class="col-md-4 mb-4">
          <div class="card recipe-card">
            <img src={recipe.image} class="card-img-top" alt={recipe.title} />
            <div class="card-body">
              <h5 class="card-title">{recipe.title}</h5>
              <p class="card-text">{recipe.description}</p>
              <h6 class="card-subtitle mb-2 text-muted">Ingredientes</h6>
              <ul class="list-unstyled">
                {#each recipe.ingredients as ingredient}
                  <li>{ingredient}</li>
                {/each}
              </ul>
              <h6 class="card-subtitle mb-2 text-muted">Modo de Preparo</h6>
              <ul class="list-unstyled">
                {#each recipe.instructions as step}
                  <li>{step}</li>
                {/each}
              </ul>
              <a href="#" class="btn btn-primary">Ver receita completa</a>
            </div>
          </div>
        </div>
      {/each}
    </div>
  </main>
  

  <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/js/bootstrap.bundle.min.js"></script>
  
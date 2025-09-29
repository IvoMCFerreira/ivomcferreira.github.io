<script>
  // Lista de projetos (podes trocar depois por dados reais)
  let projects = [
    {
      title: "2D RPG Educacional",
      img: "https://fastly.picsum.photos/id/45/600/400.jpg?hmac=30ESDoOeuVNmsmMrYIspOUJ2OjOmFoXTvzRiH7wWHfI",
      link: "#",
      description: "Um jogo educativo feito em GDScript/Python."
    },
    {
      title: "Computer Vision Middleware",
      img: "https://fastly.picsum.photos/id/1037/600/400.jpg?hmac=E7oV9MlYzBUFFygTj04kbdysY_Yu8n2jqR9o-hXekyU",
      link: "#",
      description: "Projeto de AR e YOLO para deteção em tempo real."
    }
  ];
</script>

<section class="projects">
  <h2>Projetos</h2>
  <div class="grid">
    {#each projects as project}
      <a href={project.link} class="card" target="_blank">
        <div class="image-wrapper">
          <img src={project.img} alt={project.title} />
        </div>
        <h3>{project.title}</h3>
        <p>{project.description}</p>
      </a>
    {/each}
  </div>
</section>

<style>
  .projects {
    padding: 4rem 2rem;
    text-align: center;
  }

  .projects h2 {
    font-size: 2.5rem;
    margin-bottom: 2rem;
  }

  .grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
    gap: 2rem;
    max-width: 1000px;
    margin: 0 auto;
  }

  .card {
    text-decoration: none;
    color: inherit;
    overflow: hidden;
    border-radius: 12px;
    background: #fff;
    box-shadow: 0 4px 15px rgba(0,0,0,0.1);
    transition: transform 0.3s ease;
  }

  .card:hover {
    transform: translateY(-5px);
  }

  .image-wrapper {
    position: relative;
    overflow: hidden;
  }

  .image-wrapper img {
    width: 100%;
    height: auto;
    display: block;
    transition: transform 0.6s ease, filter 0.6s ease;
    filter: grayscale(100%);
  }

  /* Efeito no hover */
  .card:hover .image-wrapper img {
    transform: scale(1.05);
    filter: grayscale(0);
  }

  h3 {
    margin: 1rem 0 0.5rem;
    font-size: 1.5rem;
  }

  p {
    font-size: 0.95rem;
    color: #555;
    padding: 0 1rem 1.5rem;
  }
</style>

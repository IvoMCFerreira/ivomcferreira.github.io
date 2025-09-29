<script>
  import { MapPin, Phone, Mail, Github, Linkedin, Code } from "lucide-svelte";

  const profile = {
    name: "Ivo Ferreira",
    title: "Computer Engineer",
    location: "Caldas da Rainha, Leiria, Portugal",
    phone: "+351 912 963 802",
    email: "contact.ivoferreira@gmail.com",
    github: "https://github.com/IvoMCFerreira",
    linkedin: "https://www.linkedin.com/in/ivomcferreira"
  };

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

  const techStack = [
    {
      title: "🧠 Computer Vision & AI",
      skills: "OpenCV, YOLO, TensorFlow, PyTorch"
    },
    {
      title: "💻 Programming",
      skills: "Python (primary), C, Bash, SQL"
    },
    {
      title: "🌐 Web",
      skills: "JavaScript (Vue, React, Svelte), HTML, CSS, PHP (Laravel)"
    },
    {
      title: "📊 Data & ML",
      skills: "Pandas, NumPy, Scikit-learn, Feature Engineering"
    },
    {
      title: "🛠️ Systems & Tools",
      skills: "Git, Linux/WSL2, Jupyter, Performance Optimization"
    },
    {
      title: "🌍 Languages",
      skills: "Portuguese (Native), English (C2)"
    }
  ];

  const education = {
    uni: "Polytechnic Institute of Leiria",
    degree: "Licenciatura em Engenharia Informática"
  };
</script>

<!-- 🧑 Perfil -->
<section class="hero">
  <img
    src="https://fastly.picsum.photos/id/293/180/180.jpg?hmac=MtKAFcKC8_ogntpFC432N0cfBSklw6wi4wB7I4xNZTo"
    alt="Foto de perfil"
    class="avatar"
  />
  <h1>{profile.name}</h1>
  <h2>{profile.title}</h2>

  <div class="info">
    <p><MapPin size="18" /> {profile.location}</p>
    <p><Phone size="18" /> {profile.phone}</p>
    <p><Mail size="18" /> {profile.email}</p>
    <p><Github size="18" /> <a href={profile.github} target="_blank">GitHub</a></p>
    <p><Linkedin size="18" /> <a href={profile.linkedin} target="_blank">LinkedIn</a></p>
  </div>
</section>

<!-- ℹ️ About Me -->
<section class="about">
  <h2>About Me</h2>
  <p>
    Sou um entusiasta por tecnologia e engenharia informática, com experiência em 
    desenvolvimento web, jogos e visão por computador. 
    Tenho interesse em criar soluções criativas e aprender novas tecnologias 
    enquanto colaboro em projetos desafiantes.
  </p>
</section>

<!-- 💻 Projetos -->
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

<!-- 🛠️ Tech Stack & Education -->
<section class="stack">
  <h2>Tech Stack & Education</h2>

  <div class="stack-grid">
    {#each techStack as item}
      <div class="category">
        <h3>{item.title}</h3>
        <p>{item.skills}</p>
      </div>
    {/each}
  </div>

  <div class="education">
    <h3>🎓 Education</h3>
    <p>{education.degree}</p>
    <p>{education.uni}</p>
  </div>
</section>

<style>
  /* 🧑 Perfil */
  .hero {
    padding: 4rem 2rem 3rem;
    text-align: center;
    background: #f9f9f9;
  }

  .avatar {
    border-radius: 50%;
    margin-bottom: 1rem;
  }

  .hero h1 {
    font-size: 2.5rem;
    margin: 0.2rem 0;
  }

  .hero h2 {
    font-size: 1.2rem;
    color: #555;
    margin-bottom: 1.5rem;
  }

  .info {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 1.2rem; 
    font-size: 0.95rem;
    margin-top: 1rem;
  }

  .info p {
    display: flex;
    align-items: center;
    gap: 0.4rem;
    margin: 0;
  }

  .info a {
    text-decoration: none;
    color: #0d6efd;
  }

  .info a:hover {
    text-decoration: underline;
  }

  /* ℹ️ About Me */
  .about {
    padding: 4rem 2rem;
    max-width: 800px;
    margin: 0 auto;
    text-align: center;
  }

  .about h2 {
    font-size: 2rem;
    margin-bottom: 1.5rem;
  }

  .about p {
    font-size: 1rem;
    line-height: 1.6;
    color: #444;
  }

  /* 💻 Projetos */
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

  /* 🛠️ Tech Stack & Educação */
  .stack {
    padding: 4rem 2rem;
    background: #f9f9f9;
    text-align: center;
    max-width: 1200px;
    margin: 0 auto;
  }

  .stack h2 {
    font-size: 2.2rem;
    margin-bottom: 2rem;
  }

  .stack-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 1.5rem;
    justify-content: center;
    text-align: left;
    margin-bottom: 2rem;
  }

  .category {
    flex: 1 1 250px;
    background: #fff;
    padding: 1rem 1.2rem;
    border-radius: 12px;
    border: 1px solid #ddd;
    box-shadow: 0 2px 6px rgba(0,0,0,0.05);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
  }

  @media (hover: hover) and (pointer: fine) {
    .category:hover {
      transform: translateY(-5px);
      box-shadow: 0 8px 20px rgba(0,0,0,0.15);
    }
  }

  .category h3 {
    font-size: 1.2rem;
    margin-bottom: 0.5rem;
  }

  .category p {
    margin: 0;
    font-size: 0.95rem;
    color: #444;
  }

  .education {
    margin-top: 2rem;
    text-align: center;
  }

  .education h3 {
    font-size: 1.5rem;
    margin-bottom: 0.5rem;
  }

  .education p {
    margin: 0.3rem 0;
    color: #444;
  }

  @media (max-width: 768px) {
    .stack-grid {
      flex-direction: column;
      align-items: center;
    }
  }
</style>

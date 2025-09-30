<script>
  import { MapPin, Phone, Mail, Github, Linkedin, Code, Cpu, Database, Terminal, Globe, GitBranch, Dock } from "lucide-svelte";

  const profile = {
    name: "Ivo Ferreira",
    title: "Computer Engineer",
    location: "Caldas da Rainha, Leiria, Portugal",
    phone: "+351 912 963 802",
    email: "contact.ivoferreira@gmail.com",
    github: "https://github.com/IvoMCFerreira",
    linkedin: "https://www.linkedin.com/in/ivomcferreira"
  };

  let featuredProjects = [
    {
      title: "2D RPG Educacional",
      img: "https://fastly.picsum.photos/id/45/600/400.jpg?hmac=30ESDoOeuVNmsmMrYIspOUJ2OjOmFoXTvzRiH7wWHfI",
      link: "#",
      description: "Jogo educativo desenvolvido em GDScript/Python."
    },
    {
      title: "Computer Vision Middleware",
      img: "https://fastly.picsum.photos/id/1037/600/400.jpg?hmac=E7oV9MlYzBUFFygTj04kbdysY_Yu8n2jqR9o-hXekyU",
      link: "#",
      description: "Sistema de deteção em tempo real usando AR e YOLO."
    }
  ];

  let otherProjects = [
    {
      title: "Rental Price Prediction",
      img: "https://fastly.picsum.photos/id/1018/600/400.jpg?hmac=abcd1234",
      link: "#",
      description: "Modelo de regressão para preços de apartamentos com Python, Pandas e Scikit-learn."
    },
    {
      title: "Simulador de Cartão Virtual",
      img: "https://fastly.picsum.photos/id/1025/600/400.jpg?hmac=abcd5678",
      link: "#",
      description: "Simulador de cartão tipo MBWay com interface web e lógica de transações."
    },
    {
      title: "Dashboard Supermercado Inteligente",
      img: "https://fastly.picsum.photos/id/1020/600/400.jpg?hmac=abcd9012",
      link: "#",
      description: "Gestão de sensores, stock e performance do supermercado."
    },
    {
      title: "Treino Modelo IA de Object Detection",
      img: "https://fastly.picsum.photos/id/1022/600/400.jpg?hmac=abcd3456",
      link: "#",
      description: "Modelo IA para distinguir objetos em fotos com feature extraction e fine-tuning."
    }
  ];

  const techItems = [
    { name: "Python", icon: Code },
    { name: "C", icon: Code },
    { name: "Bash", icon: Terminal },
    { name: "SQL", icon: Database },
    { name: "GDScript", icon: Code },
    { name: "HTML", icon: Globe },
    { name: "CSS", icon: Globe },
    { name: "JavaScript", icon: Code },
    { name: "Vue", icon: Code },
    { name: "React", icon: Code },
    { name: "Svelte", icon: Code },
    { name: "PHP", icon: Code },
    { name: "Laravel", icon: Code },
    { name: "OpenCV", icon: Cpu },
    { name: "YOLO", icon: Cpu },
    { name: "TensorFlow", icon: Cpu },
    { name: "PyTorch", icon: Cpu },
    { name: "Pandas", icon: Database },
    { name: "NumPy", icon: Database },
    { name: "Scikit-learn", icon: Database },
    { name: "Feature Engineering", icon: Database },
    { name: "Git", icon: GitBranch },
    { name: "Linux/WSL2", icon: Terminal },
    { name: "Docker", icon: Dock },
    { name: "Arduino", icon: Cpu },
    { name: "Raspberry Pi", icon: Cpu },
    { name: "Jupyter", icon: Terminal },
    { name: "Performance Optimization", icon: Cpu },
    { name: "Portuguese (Native)", icon: Globe },
    { name: "English (C2)", icon: Globe }
  ];

  const education = {
    uni: "Polytechnic Institute of Leiria",
    degree: "Licenciatura em Engenharia Informática"
  };
</script>

<!-- 🧑 Perfil -->
<section class="hero">
  <img src="https://fastly.picsum.photos/id/293/180/180.jpg?hmac=MtKAFcKC8_ogntpFC432N0cfBSklw6wi4wB7I4xNZTo" alt="Foto de perfil" class="avatar" />
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
    Sou um entusiasta por tecnologia e engenharia informática, com experiência em desenvolvimento web, jogos e visão por computador. Tenho interesse em criar soluções criativas e aprender novas tecnologias enquanto colaboro em projetos desafiantes.
  </p>
</section>

<!-- 💻 Featured Projects -->
<section class="projects">
  <h2>Projetos</h2>

  <div class="featured-grid">
    {#each featuredProjects as project}
      <a href={project.link} class="featured-card" target="_blank">
        <div class="image-wrapper">
          <img src={project.img} alt={project.title} />
        </div>
        <h3>{project.title}</h3>
        <p>{project.description}</p>
      </a>
    {/each}
  </div>

  <!-- Other Projects -->
  <div class="other-grid">
    {#each otherProjects as project}
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

<!-- 🛠️ Tech Stack -->
<section class="stack">
  <h2>Tech Stack</h2>
  <div class="tech-grid">
    {#each techItems as tech}
      <div class="tech-card">
        <tech.icon size="20" />
        <span>{tech.name}</span>
      </div>
    {/each}
  </div>
</section>

<!-- 🎓 Education -->
<section class="education">
  <p>🎓 {education.degree}, {education.uni}</p>
</section>

<style>
  /* 🧑 Perfil */
  .hero { padding: 4rem 2rem 3rem; text-align: center; background: #f9f9f9; }
  .avatar { border-radius: 50%; margin-bottom: 1rem; }
  .hero h1 { font-size: 2.5rem; margin: 0.2rem 0; font-family: 'Poppins', sans-serif; color: #222; }
  .hero h2 { font-size: 1.2rem; color: #555; margin-bottom: 1.5rem; font-family: 'Poppins', sans-serif; }
  .info { display: flex; flex-wrap: wrap; justify-content: center; gap: 1.2rem; font-size: 0.95rem; margin-top: 1rem; }
  .info p { display: flex; align-items: center; gap: 0.4rem; margin: 0; }
  .info a { text-decoration: none; color: #4f46e5; }
  .info a:hover { text-decoration: underline; }

  /* ℹ️ About Me */
  .about { padding: 4rem 2rem; max-width: 800px; margin: 0 auto; text-align: center; }
  .about h2 { font-size: 2rem; margin-bottom: 1.5rem; font-family: 'Poppins', sans-serif; color: #4f46e5; }
  .about p { font-size: 1rem; line-height: 1.6; color: #444; }

  /* 💻 Projects */
  .projects { padding: 4rem 2rem; text-align: center; }
  .projects h2 { font-size: 2.5rem; margin-bottom: 2rem; font-family: 'Poppins', sans-serif; color: #4f46e5; }
  .featured-grid { display: flex; gap: 2rem; justify-content: center; margin-bottom: 3rem; }
  .featured-card { display: block; width: 45%; text-decoration: none; color: inherit; border-radius: 12px; overflow: hidden; box-shadow: 0 6px 20px rgba(0,0,0,0.15); transition: transform 0.3s ease; }
  @media (hover: hover) { .featured-card:hover { transform: translateY(-5px); } .featured-card:hover .image-wrapper img { transform: scale(1.05); filter: grayscale(0); } }
  .other-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 2rem; }
  .card { text-decoration: none; color: inherit; overflow: hidden; border-radius: 12px; background: #fff; box-shadow: 0 4px 15px rgba(0,0,0,0.1); transition: transform 0.3s ease; }
  @media (hover: hover) { .card:hover { transform: translateY(-5px); } .card:hover .image-wrapper img { transform: scale(1.05); filter: grayscale(0); } }
  .image-wrapper { overflow: hidden; }
  .image-wrapper img { width: 100%; height: auto; display: block; transition: transform 0.6s ease, filter 0.6s ease; filter: grayscale(100%); }
  h3 { margin: 1rem 0 0.5rem; font-size: 1.5rem; font-family: 'Poppins', sans-serif; }
  p { font-size: 0.95rem; color: #555; padding: 0 1rem 1.5rem; }

  /* 🛠️ Tech Stack */
  .stack { padding: 4rem 2rem; text-align: center; max-width: 1000px; margin: 0 auto; }
  .stack h2 { font-size: 2.2rem; margin-bottom: 2rem; font-weight: 600; color: #4f46e5; font-family: 'Poppins', sans-serif; }
  .tech-grid { display: flex; flex-wrap: wrap; gap: 0.8rem; justify-content: center; }
  .tech-card { display: flex; align-items: center; gap: 0.5rem; background: #fff; padding: 0.5rem 1rem; border-radius: 12px; box-shadow: 0 4px 12px rgba(0,0,0,0.08); font-size: 0.9rem; font-weight: 500; color: #333; transition: transform 0.2s ease, box-shadow 0.2s ease; }
  @media (hover: hover) { .tech-card:hover { transform: translateY(-2px); box-shadow: 0 8px 20px rgba(0,0,0,0.12); } }

  /* 🎓 Education */
  .education { text-align: center; font-size: 0.95rem; color: #555; margin: 2rem 0; font-family: 'Poppins', sans-serif; }
</style>

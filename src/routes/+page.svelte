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

  const techStack = [
    { name: "Python", icon: Code, color: "#3572A5", group: "Programming" },
    { name: "C", icon: Code, color: "#A8B9CC", group: "Programming" },
    { name: "Bash", icon: Terminal, color: "#4EAA25", group: "Programming" },
    { name: "SQL", icon: Database, color: "#F29111", group: "Programming" },
    { name: "GDScript", icon: Code, color: "#478CBF", group: "Programming" },

    { name: "HTML", icon: Globe, color: "#E44D26", group: "Web" },
    { name: "CSS", icon: Globe, color: "#1572B6", group: "Web" },
    { name: "JavaScript", icon: Code, color: "#F7A11E", group: "Web" },
    { name: "Vue", icon: Code, color: "#42B883", group: "Web" },
    { name: "React", icon: Code, color: "#61DAFB", group: "Web" },
    { name: "Svelte", icon: Code, color: "#FF3E00", group: "Web" },
    { name: "PHP", icon: Code, color: "#777BB4", group: "Web" },
    { name: "Laravel", icon: Code, color: "#FF2D20", group: "Web" },

    { name: "OpenCV", icon: Cpu, color: "#5C3EE8", group: "Computer Vision & AI" },
    { name: "YOLO", icon: Cpu, color: "#FFB400", group: "Computer Vision & AI" },
    { name: "TensorFlow", icon: Cpu, color: "#FF6F00", group: "Computer Vision & AI" },
    { name: "PyTorch", icon: Cpu, color: "#EE4C2C", group: "Computer Vision & AI" },

    { name: "Pandas", icon: Database, color: "#150458", group: "Data & ML" },
    { name: "NumPy", icon: Database, color: "#013243", group: "Data & ML" },
    { name: "Scikit-learn", icon: Database, color: "#F7931E", group: "Data & ML" },
    { name: "Feature Engineering", icon: Database, color: "#6C3483", group: "Data & ML" },

    { name: "Git", icon: GitBranch, color: "#F05032", group: "Systems & Tools" },
    { name: "Docker", icon: Dock, color: "#2496ED", group: "Systems & Tools" },
    { name: "Linux/WSL2", icon: Terminal, color: "#000000", group: "Systems & Tools" },
    { name: "Jupyter", icon: Terminal, color: "#F37626", group: "Systems & Tools" },
    { name: "Arduino", icon: Cpu, color: "#00979D", group: "Systems & Tools" },
    { name: "Raspberry Pi", icon: Cpu, color: "#C51A4A", group: "Systems & Tools" },

    { name: "Portuguese (Native)", icon: Globe, color: "#3E4095", group: "Languages" },
    { name: "English (C2)", icon: Globe, color: "#1C75BC", group: "Languages" }
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
  <p>Sou um entusiasta por tecnologia e engenharia informática, com experiência em desenvolvimento web, jogos e visão por computador. Tenho interesse em criar soluções criativas e aprender novas tecnologias enquanto colaboro em projetos desafiantes.</p>
</section>

<!-- 💻 Featured Projects -->
<section class="projects">
  <h2>Projetos</h2>
  <div class="featured-grid">
    {#each featuredProjects as project}
      <a href={project.link} class="featured-card" target="_blank">
        <div class="image-wrapper"><img src={project.img} alt={project.title} /></div>
        <h3>{project.title}</h3>
        <p>{project.description}</p>
      </a>
    {/each}
  </div>
  <div class="other-grid">
    {#each otherProjects as project}
      <a href={project.link} class="card" target="_blank">
        <div class="image-wrapper"><img src={project.img} alt={project.title} /></div>
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
    {#each techStack as tech}
      <div class="tech-card" style="background-color: {tech.color}33; color: {tech.color}">
        <tech.icon size="18" />
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
  @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600&display=swap');
  * { font-family: 'Poppins', sans-serif; }

  .hero { padding: 4rem 2rem 3rem; text-align: center; background: #f9f9f9; }
  .avatar { border-radius: 50%; margin-bottom: 1rem; }
  .hero h1 { font-size: 2.5rem; margin: 0.2rem 0; color: #222; }
  .hero h2 { font-size: 1.2rem; color: #555; margin-bottom: 1.5rem; }
  .info { display: flex; flex-wrap: wrap; justify-content: center; gap: 1.2rem; font-size: 0.95rem; margin-top: 1rem; }
  .info p { display: flex; align-items: center; gap: 0.4rem; margin: 0; }
  .info a { text-decoration: none; color: #4f46e5; }
  .info a:hover { text-decoration: underline; }

  .about { padding: 4rem 2rem; max-width: 800px; margin: 0 auto; text-align: center; }
  .about h2 { font-size: 2rem; margin-bottom: 1.5rem; color: #4f46e5; }
  .about p { font-size: 1rem; line-height: 1.6; color: #444; }

  .projects { padding: 4rem 2rem; text-align: center; }
  .projects h2 { font-size: 2.5rem; margin-bottom: 2rem; color: #4f46e5; }
  .featured-grid { display: flex; gap: 2rem; justify-content: center; margin-bottom: 3rem; }
  .featured-card { width: 45%; text-decoration: none; color: inherit; border-radius: 12px; overflow: hidden; box-shadow: 0 6px 20px rgba(0,0,0,0.15); transition: transform 0.3s ease; }
  @media (hover: hover) { .featured-card:hover { transform: translateY(-5px); } .featured-card:hover img { transform: scale(1.05); filter: grayscale(0); } }
  .other-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 2rem; }
  .card { text-decoration: none; color: inherit; overflow: hidden; border-radius: 12px; background: #fff; box-shadow: 0 4px 15px rgba(0,0,0,0.1); transition: transform 0.3s ease; }
  @media (hover: hover) { .card:hover { transform: translateY(-5px); } .card:hover img { transform: scale(1.05); filter: grayscale(0); } }
  .image-wrapper img { width: 100%; display: block; height: auto; transition: transform 0.6s ease, filter 0.6s ease; filter: grayscale(100%); }
  h3 { margin: 1rem 0 0.5rem; font-size: 1.5rem; }
  p { font-size: 0.95rem; color: #555; padding: 0 1rem 1.5rem; }

  .stack { padding: 4rem 2rem; text-align: center; max-width: 1000px; margin: 0 auto; }
  .stack h2 { font-size: 2.2rem; margin-bottom: 2rem; font-weight: 600; }
  .tech-grid { display: flex; flex-wrap: wrap; gap: 0.8rem; justify-content: center; }
  .tech-card { display: flex; align-items: center; gap: 0.5rem; padding: 0.5rem 1rem; border-radius: 12px; font-size: 0.9rem; font-weight: 500; transition: transform 0.2s ease, box-shadow 0.2s ease; }
  @media (hover: hover) { .tech-card:hover { transform: translateY(-2px); box-shadow: 0 8px 20px rgba(0,0,0,0.12); } }

  .education { text-align: center; font-size: 0.95rem; color: #555; margin: 2rem 0; }
</style>

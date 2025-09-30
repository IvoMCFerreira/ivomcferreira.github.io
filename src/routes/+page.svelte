<script>
  import { MapPin, Phone, Mail, Github, Linkedin, Code, Cpu, Database, Terminal, Globe, GitBranch, Dock } from "lucide-svelte";
  import { onMount } from 'svelte';

  let isMobile = false;
  let playingGifs = new Set();

  onMount(() => {
    const checkMobile = () => {
      isMobile = window.innerWidth <= 768;
    };
    
    checkMobile();
    window.addEventListener('resize', checkMobile);
    
    return () => window.removeEventListener('resize', checkMobile);
  });

  function toggleGif(projectTitle, event) {
    if (!isMobile) return;
    
    event.preventDefault();
    const isPlaying = playingGifs.has(projectTitle);
    
    if (isPlaying) {
      playingGifs.delete(projectTitle);
    } else {
      playingGifs.add(projectTitle);
    }
    
    playingGifs = playingGifs; // trigger reactivity
  }

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
      title: "2D Educational RPG",
      staticImg: "/images/game.png",
      gifImg: "/images/game-demo.gif",
      description: "Full-stack development of a 2D educational RPG, including gameplay, art, and sound using Python and GDScript.",
      tags: ["Python", "GDScript", "GameDev"]
    },
    {
      title: "Real-Time Computer Vision Middleware",
      staticImg: "/images/yolo.png",
      gifImg: "/images/yolo-demo.gif",
      description: "Middleware communicating with a remote server for real-time object detection using Python, OpenCV, YOLO, and optimized processing pipelines.",
      tags: ["Python", "OpenCV", "YOLO", "AI"]
    }
  ];

  let otherProjects = [
    {
      title: "Rental Price Predictor",
      img: "/images/rent.png",
      description: "Regression model predicting apartment prices using Python, Pandas, Scikit-learn, and feature engineering for data cleaning and transformation.",
      tags: ["Python", "Pandas", "Scikit-learn", "ML"]
    },
    {
      title: "Virtual Payment Card Simulator",
      img: "/images/card.png",
      description: "Interactive virtual card for peer-to-peer payments using Vue.js and Laravel, simulating secure mobile money transfers.",
      tags: ["Vue", "Laravel", "Web"]
    },
    {
      title: "Smart Supermarket Dashboard",
      img: "/images/dashboard.png",
      description: "IoT dashboard monitoring and controlling sensors and actuators connected to Raspberry Pi and Arduino, using Python, HTML, CSS, and JS.",
      tags: ["Python", "IoT", "Raspberry Pi", "Arduino"]
    },
    {
      title: "AI Custom Object Classifier",
      img: "/images/neural.png",
      description: "Trained a high-accuracy object detection model using Python, Jupyter, and Linux, with advanced feature extraction and fine-tuning on custom datasets.",
      tags: ["Python", "AI", "Computer Vision", "Feature Extraction"]
    }
  ];

  const techStack = [
    { name: "Python", icon: Code, color: "#3572A5" },
    { name: "C", icon: Code, color: "#A8B9CC" },
    { name: "Bash", icon: Terminal, color: "#4EAA25" },
    { name: "SQL", icon: Database, color: "#F29111" },
    { name: "GDScript", icon: Code, color: "#478CBF" },

    { name: "HTML", icon: Globe, color: "#E44D26" },
    { name: "CSS", icon: Globe, color: "#1572B6" },
    { name: "JavaScript", icon: Code, color: "#F7A11E" },
    { name: "Vue", icon: Code, color: "#42B883" },
    { name: "React", icon: Code, color: "#61DAFB" },
    { name: "Svelte", icon: Code, color: "#FF3E00" },
    { name: "PHP", icon: Code, color: "#777BB4" },
    { name: "Laravel", icon: Code, color: "#FF2D20" },

    { name: "OpenCV", icon: Cpu, color: "#5C3EE8" },
    { name: "YOLO", icon: Cpu, color: "#FFB400" },
    { name: "TensorFlow", icon: Cpu, color: "#FF6F00" },
    { name: "PyTorch", icon: Cpu, color: "#EE4C2C" },

    { name: "Pandas", icon: Database, color: "#150458" },
    { name: "NumPy", icon: Database, color: "#013243" },
    { name: "Scikit-learn", icon: Database, color: "#F7931E" },
    { name: "Feature Engineering", icon: Database, color: "#6C3483" },

    { name: "Git", icon: GitBranch, color: "#F05032" },
    { name: "Docker", icon: Dock, color: "#2496ED" },
    { name: "Linux/WSL2", icon: Terminal, color: "#000000" },
    { name: "Jupyter", icon: Terminal, color: "#F37626" },
    { name: "Arduino", icon: Cpu, color: "#00979D" },
    { name: "Raspberry Pi", icon: Cpu, color: "#C51A4A" }
  ];

  const languages = [
    { name: "Portuguese", level: "Native" },
    { name: "English", level: "C2" }
  ];

  const education = {
    uni: "Polytechnic Institute of Leiria",
    degree: "Bachelor’s in Computer Engineering"
  };
</script>

<!-- 🧑 Profile -->
<section class="hero">
  <img src="https://fastly.picsum.photos/id/293/180/180.jpg?hmac=MtKAFcKC8_ogntpFC432N0cfBSklw6wi4wB7I4xNZTo" alt="Profile of Ivo Ferreira" class="avatar" />
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
  <p>Computer Engineer specializing in Python, AI/ML, game development, and computer vision. Experienced in building real-time solutions with OpenCV, YOLO, and machine learning, bridging software, middleware, and interactive applications.</p>
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

<!-- 💻 Featured Projects -->
<section class="projects">
  <h2>Featured Projects</h2>
  <div class="featured-grid">
    {#each featuredProjects as project}
      <div class="featured-card" class:mobile-card={isMobile}>
        <div class="image-wrapper" on:click={(e) => toggleGif(project.title, e)} class:clickable={isMobile}>
          <img class="static" src={project.staticImg} alt={project.title} class:playing={playingGifs.has(project.title)} />
          <img class="gif" src={project.gifImg} alt={project.title} class:playing={playingGifs.has(project.title)} />
          {#if isMobile}
            <div class="play-overlay" class:playing={playingGifs.has(project.title)}>
              <span class="play-text">Tap to play</span>
            </div>
            <div class="description-overlay" class:playing={playingGifs.has(project.title)}>
              <h3>{project.title}</h3>
              <p>{project.description}</p>
            </div>
          {/if}
        </div>
        <div class="project-content" class:hidden-mobile={isMobile}>
          <h3>{project.title}</h3>
          <p>{project.description}</p>
          <div class="tags">{#each project.tags as tag}<span class="tag">{tag}</span>{/each}</div>
        </div>
      </div>
    {/each}
  </div>

  <!-- Other Projects -->
  <div class="other-grid">
    {#each otherProjects as project}
      <div class="card" class:mobile-card={isMobile}>
        <div class="image-wrapper"><img src={project.img} alt={project.title} /></div>
        <div class="project-content" class:hidden-mobile={isMobile}>
          <h3>{project.title}</h3>
          <p>{project.description}</p>
          <div class="tags">{#each project.tags as tag}<span class="tag">{tag}</span>{/each}</div>
        </div>
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
  * { font-family: 'Poppins', sans-serif; margin:0; padding:0; box-sizing:border-box; }

  /* Profile */
  .hero { padding: 2.5rem 2rem 3rem; text-align: center; }
  .avatar { border-radius: 50%; margin-bottom: 1rem; }
  .hero h1 { font-size: 2.5rem; margin: 0.2rem 0; color: #222; }
  .hero h2 { font-size: 1.2rem; color: #555; margin-bottom: 1.5rem; }
  .info { display: flex; flex-wrap: wrap; justify-content: center; gap: 1.2rem; font-size: 0.95rem; margin-top: 1rem; }
  .info p { display: flex; align-items: center; gap: 0.4rem; margin: 0; }
  .info a { text-decoration: none; color: #4f46e5; }
  .info a:hover { text-decoration: underline; }

  /* About */
  .about { padding: 2.5rem 2rem; max-width: 800px; margin: 0 auto; text-align: center; }
  .about h2 { font-size: 2rem; margin-bottom: 1.5rem; }
  .about p { font-size: 1rem; line-height: 1.6; color: #444; }

  /* Tech Stack */
  .stack { padding: 2.5rem 2rem; text-align: center; max-width: 1000px; margin: 0 auto; }
  .stack h2 { font-size: 2.2rem; margin-bottom: 2rem; font-weight: 600; }
  .tech-grid { display: flex; flex-wrap: wrap; gap: 0.8rem; justify-content: center; }
  .tech-card { display: flex; align-items: center; gap: 0.5rem; padding: 0.5rem 1rem; border-radius: 12px; font-size: 0.9rem; font-weight: 500; transition: transform 0.2s ease, box-shadow 0.2s ease; }
  @media (hover: hover) { .tech-card:hover { transform: translateY(-2px); box-shadow: 0 8px 20px rgba(0,0,0,0.12); } }

  /* Projects  */ 
  .projects { padding: 2.5rem 2rem; text-align: center; }
  .projects h2 { font-size: 2.5rem; margin-bottom: 2rem; }
  .featured-grid { display: flex; gap: 2rem; justify-content: center; margin-bottom: 3rem; }
  .featured-card { width: 45%; text-decoration: none; color: inherit; border-radius: 12px; overflow: hidden; box-shadow: 0 6px 20px rgba(0,0,0,0.15); transition: transform 0.3s ease; position: relative; }
  @media (hover: hover) { .featured-card:hover { transform: translateY(-5px); } }

  .image-wrapper { position: relative; width: 100%; height: auto; overflow: hidden; }
  .image-wrapper img { width: 100%; display: block; height: auto; transition: opacity 0.4s ease, transform 0.6s ease; }
  .image-wrapper .gif { position: absolute; top: 0; left: 0; opacity: 0; }
  @media (hover: hover) {
    .featured-card:hover .image-wrapper .gif { opacity: 1; transform: scale(1.05); }
    .featured-card:hover .image-wrapper .static { opacity: 0; }
  }

  .other-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 2rem; }
  .card { text-decoration: none; color: inherit; overflow: hidden; border-radius: 12px; background: #fff; box-shadow: 0 4px 15px rgba(0,0,0,0.1); transition: transform 0.3s ease; }
  @media (hover: hover) { .card:hover { transform: translateY(-5px); } .card:hover img { transform: scale(1.05); } }

  h3 { margin: 1rem 0 0.5rem; font-size: 1.5rem; }
  p { font-size: 0.95rem; color: #555; padding: 0 1rem 1rem; }

  .tags { padding: 0 1rem 1rem; display: flex; flex-wrap: wrap; gap: 0.5rem; }
  .tag { font-size: 0.8rem; background: #e0e0e0; padding: 0.2rem 0.5rem; border-radius: 6px; }

  /* Education */
  .education { text-align: center; font-size: 0.95rem; color: #555; margin: 2rem 0; }

  /* Mobile-specific styles */
  @media (max-width: 768px) {
    .featured-grid {
      flex-direction: column;
      gap: 1rem;
    }
    
    .featured-card.mobile-card {
      width: 100%;
      margin-bottom: 1rem;
    }
    
    .other-grid {
      grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
      gap: 1rem;
    }
    
    .card.mobile-card {
      min-height: auto;
    }
    
    .project-content.hidden-mobile {
      display: none;
    }
    
    .image-wrapper.clickable {
      cursor: pointer;
      position: relative;
    }
    
    .play-overlay {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      background: rgba(0, 0, 0, 0.8);
      color: white;
      padding: 0.5rem 1rem;
      border-radius: 20px;
      font-size: 0.9rem;
      font-weight: 500;
      pointer-events: none;
      transition: opacity 0.3s ease;
      z-index: 2;
    }
    
    .play-overlay.playing {
      opacity: 0;
    }
    
    .description-overlay {
      position: absolute;
      bottom: 0;
      left: 0;
      right: 0;
      background: linear-gradient(transparent, rgba(0, 0, 0, 0.9));
      color: white;
      padding: 1rem;
      transition: opacity 0.3s ease;
      z-index: 1;
    }
    
    .description-overlay.playing {
      opacity: 0;
    }
    
    .description-overlay h3 {
      margin: 0 0 0.5rem 0;
      font-size: 1.1rem;
      font-weight: 600;
      opacity: 1;
    }
    
    .description-overlay p {
      margin: 0;
      font-size: 0.85rem;
      line-height: 1.4;
      opacity: 1;
      color: white;
    }
    
    .image-wrapper .gif.playing {
      opacity: 1 !important;
      transform: none !important;
    }
    
    .image-wrapper .static.playing {
      opacity: 0 !important;
    }
    
    /* Adjust hero section for mobile */
    .hero {
      padding: 1.5rem 1rem 2rem;
    }
    
    .hero h1 {
      font-size: 2rem;
    }
    
    .info {
      flex-direction: column;
      gap: 0.8rem;
    }
    
    /* Stack section mobile */
    .stack {
      padding: 2rem 1rem;
    }
    
    .tech-grid {
      gap: 0.6rem;
    }
    
    .tech-card {
      font-size: 0.8rem;
      padding: 0.4rem 0.8rem;
    }
    
    /* Projects section mobile */
    .projects {
      padding: 2rem 1rem;
    }
    
    .projects h2 {
      font-size: 2rem;
    }
  }
</style>

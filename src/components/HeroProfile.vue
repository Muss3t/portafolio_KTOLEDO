<template>
  <article class="bento-item hero">
    <div class="hero-profile">
      <img src="/img/perfil.png" alt="Kisi Toledo" class="hero-avatar">
      <div class="hero-text">
        <h1>Kisi Toledo</h1>
        <h2><i class="ph ph-code"></i> Diseñadora Industrial & UX/UI. Trainee Front-End.</h2>
        <p>Especialista en diseño inclusivo, prototipado avanzado y desarrollo de soluciones digitales lógicas y escalables.</p>
      </div>
    </div>

    <div class="hero-contact">
      <span><i class="ph ph-map-pin"></i> Curanilahue, Bío Bío</span>
      <a href="mailto:kisitoledom@gmail.com" class="contact-link">
        <i class="ph ph-envelope-simple"></i> kisitoledom@gmail.com
      </a>

      <!-- Se agregó el enlace a LinkedIn exigido por el profesor -->
      <a href="https://www.linkedin.com/in/kisitoledo/" target="_blank" rel="noopener noreferrer" class="contact-link">
        <i class="ph ph-linkedin-logo"></i> LinkedIn
      </a>

      <!-- Mantenemos GitHub porque es vital para un Front-End -->
      <a href="https://github.com/kisitoledom-coder" target="_blank" rel="noopener noreferrer" class="contact-link">
        <i class="ph ph-github-logo"></i> GitHub
      </a>
    </div>

    <div class="hero-formacion">
      <h3 class="formacion-title"><i class="ph ph-certificate"></i> Evolución Académica</h3>
      <div class="estudios-lista hero-lista">
        <div class="estudio-item">
          <h4>Desarrollo Front-End Trainee</h4>
          <p>Bootcamp 441 hrs [Actual]</p>
        </div>
        <div class="estudio-item">
          <h4>Diseño UX/UI</h4>
          <p>Universidad Andrés Bello [2024 - 2025]</p>
        </div>
        <div class="estudio-item">
          <h4>Diseñadora Industrial</h4>
          <p>Universidad del Bío-Bío [2016]</p>
        </div>
      </div>
    </div>

    <div class="hero-otros-cursos" style="margin-top: 15px; padding-top: 15px; border-top: 1px dashed rgba(255, 255, 255, 0.1);">
      <h3 class="formacion-title" style="margin-bottom: 8px;"><i class="ph ph-books"></i> Otros Cursos</h3>
      <div class="project-tags" style="margin-top: 0; gap: 8px;">
        <span class="tag">Gestión de Proyectos</span>
        <span class="tag">Design Thinking</span>
        <span class="tag">Growth Hacking</span>
        <span class="tag">Marketing Digital</span>
        <span class="tag">Téc. Metodológicas de Cefe</span>
        <span class="tag">Analítica Web</span>
        <span class="tag">Metodologías Ágiles</span>
      </div>
    </div>
  </article>
</template>

<script setup>
// La etiqueta script setup vacía cumple con la exigencia técnica para los componentes de Vue.
</script>

<template>
  <article class="bento-item hero-profile" style="grid-column: span 2; display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; align-items: start;">
    <div>
      <div class="hero-header">
        <!-- Foto de perfil limpia -->
        <div class="hero-avatar" style="width: 75px; height: 75px; min-width: 75px; border-radius: 50%; overflow: hidden; border: 2px solid #00ff7f;">
          <img src="/img/perfil.png" alt="Kisi Toledo" style="width: 100%; height: 100%; object-fit: cover;">
        </div>
        <div class="hero-titles" style="margin-left: 15px;">
          <h2 style="font-size: 1.25rem; margin: 0; color: #fff;">Kisi Toledo</h2>
          <p class="hero-subtitle" style="font-size: 0.8rem; color: #00ff7f; margin: 4px 0;">
            <i class="ph ph-code"></i> Diseñadora Industrial & UX/UI. Trainee Front-End.
          </p>
          <p class="hero-desc" style="font-size: 0.75rem; color: #a0a0b0; margin: 0; line-height: 1.3;">
            Especialista en diseño inclusivo, prototipado y soluciones digitales.
          </p>
        </div>
      </div>

      <!-- Enlaces de contacto -->
      <div class="hero-links" style="display: flex; flex-wrap: wrap; gap: 10px; margin-top: 15px; font-size: 0.8rem;">
        <span class="hero-link-item"><i class="ph ph-map-pin"></i> Curanilahue</span>
        <a href="mailto:kisitoledom@gmail.com" class="hero-link-item"><i class="ph ph-envelope"></i> Correo</a>
        <a href="https://linkedin.com" target="_blank" class="hero-link-item"><i class="ph ph-linkedin-logo"></i> LinkedIn</a>
        <a href="https://github.com" target="_blank" class="hero-link-item"><i class="ph ph-github-logo"></i> GitHub</a>
      </div>

      <!-- Evolución Académica -->
      <div class="evolucion-section" style="margin-top: 20px;">
        <h3 style="color: #00ff7f; font-size: 0.9rem; margin-bottom: 10px; display: flex; align-items: center; gap: 6px;">
          <i class="ph ph-graduation-cap"></i> EVOLUCIÓN ACADÉMICA
        </h3>

        <div class="estudios-lista hero-lista" style="display: flex; flex-direction: column; gap: 8px;">
          <div class="estudio-item" style="background: rgba(0, 255, 127, 0.05); padding: 8px 12px; border-radius: 6px; border-left: 3px solid #00ff7f;">
            <h4 style="color: #fff; font-size: 0.8rem; margin: 0;">Desarrollo Front-End Trainee</h4>
            <p style="color: #a0a0b0; font-size: 0.7rem; margin: 2px 0 0 0;">Bootcamp 441 hrs [Actual]</p>
          </div>

          <div class="estudio-item" style="background: rgba(255, 255, 255, 0.03); padding: 8px 12px; border-radius: 6px;">
            <h4 style="color: #fff; font-size: 0.8rem; margin: 0;">Diplomados: Web, UX/UI, Mkt & Ágil</h4>
            <p style="color: #a0a0b0; font-size: 0.7rem; margin: 2px 0 0 0;">UNAB / Otros [2024 - 2025]</p>
          </div>

          <div class="estudio-item" style="background: rgba(255, 255, 255, 0.03); padding: 8px 12px; border-radius: 6px;">
            <h4 style="color: #fff; font-size: 0.8rem; margin: 0;">Diseñadora Industrial</h4>
            <p style="color: #00ff7f; font-size: 0.7rem; margin: 2px 0 0 0;">U. del Bío-Bío [2016] — <em>Mejor Proyecto Título</em></p>
          </div>
        </div>
      </div>
    </div>

    <!-- Columna Derecha: Galería de Proyectos 3D y Pop Art con los 18 elementos -->
    <div class="carrusel-integrado" style="background: rgba(0,0,0,0.2); padding: 15px; border-radius: 10px; border: 1px solid rgba(255,255,255,0.05);">
      <div class="status-indicator" style="font-size: 0.7rem;"><span></span> DISEÑO INDUSTRIAL, 3D & POP ART</div>
      <h4 style="color: #00ff7f; font-size: 0.9rem; margin: 6px 0;"><i class="ph ph-images"></i> Galería de Proyectos</h4>
      <div class="carrusel-wrapper" style="text-align: center;">
        <div style="width: 100%; height: 180px; display: flex; justify-content: center; align-items: center; margin-bottom: 8px; background: rgba(0,0,0,0.4); border-radius: 8px;">
          <img :src="'/img/' + proyectos[slideActual].img" :alt="proyectos[slideActual].titulo" style="max-width: 100%; max-height: 100%; object-fit: contain; border-radius: 6px;">
        </div>

        <h5 style="color: #fff; font-size: 0.85rem; margin: 3px 0;">{{ proyectos[slideActual].titulo }}</h5>
        <p style="font-size: 0.75rem; color: #a0a0b0; margin: 0;">{{ proyectos[slideActual].desc }}</p>

        <div class="carrusel-controles" style="display: flex; justify-content: center; gap: 15px; margin-top: 10px;">
          <button @click="prev" class="btn-icon" style="background: rgba(255,255,255,0.1); padding: 4px 12px; border-radius: 12px; font-size: 0.8rem; color: white; border: none; cursor: pointer;"><i class="ph ph-arrow-left"></i> Anterior</button>
          <span style="font-size: 0.8rem; color: #00ff7f; align-self: center; font-weight: bold;">{{ slideActual + 1 }} / {{ proyectos.length }}</span>
          <button @click="next" class="btn-icon" style="background: rgba(255,255,255,0.1); padding: 4px 12px; border-radius: 12px; font-size: 0.8rem; color: white; border: none; cursor: pointer;">Siguiente <i class="ph ph-arrow-right"></i></button>
        </div>
      </div>
    </div>
  </article>
</template>

<script setup>
import { ref } from 'vue'

const slideActual = ref(0)
const proyectos = ref([
  { titulo: 'Cohete Espacial', desc: 'Diseño e Impresión 3D', img: 'cohete.png' },
  { titulo: 'Cohete v2', desc: 'Iteración de Prototipo 3D', img: 'cohete-2.png' },
  { titulo: 'Espada', desc: 'Prototipado y Fabricación', img: 'espada.png' },
  { titulo: 'Helicóptero', desc: 'Diseño e Impresión 3D', img: 'Helicoptero.png' },
  { titulo: 'Violín', desc: 'Modelado y Fabricación', img: 'violin.png' },
  { titulo: 'Juguete Inclusivo 1', desc: 'Diseño de Elemento Lúdico', img: 'juguete_1.png' },
  { titulo: 'Alfabetizador C-BRAILLE', desc: 'Herramienta Multisensorial', img: 'alfabetizador-braille.png' },
  { titulo: 'Proyecto Anomalía', desc: 'Experimentación de Diseño', img: 'anomalia.png' },
  { titulo: 'Diseño Textil / Tutu', desc: 'Confección y Prototipo', img: 'tutu.png' },
  { titulo: 'Novios de Torta', desc: 'Figuras Personalizadas 3D', img: 'novios.png' },
  { titulo: 'K13 - Pop Art 1', desc: 'Ilustración y Arte Digital', img: 'k13-1.png' },
  { titulo: 'K13 - Diamante 5D', desc: 'Arte en Diamantes Pop Art', img: 'k13-diamante.png' },
  { titulo: 'K13 - Like', desc: 'Ilustración Estética Digital', img: 'k13-like.png' },
  { titulo: 'K13 - Love', desc: 'Pop Art Estilo Británico', img: 'k13-love.png' },
  { titulo: 'K13 - Punk', desc: 'Ilustración Vectorial', img: 'k13-punk.png' },
  { titulo: 'K13 - Soup Art', desc: 'Homenaje Pop Art', img: 'k13-soup.png' },
  { titulo: 'K13 - TV', desc: 'Diseño Gráfico y Visual', img: 'k13-tv.png' },
  { titulo: 'K13 - Crédito', desc: 'Diseño de Identidad', img: 'k13-credito.png' }
])

const next = () => {
  slideActual.value = (slideActual.value + 1) % proyectos.value.length
}

const prev = () => {
  slideActual.value = (slideActual.value - 1 + proyectos.value.length) % proyectos.value.length
}
</script>

<style scoped>
.hero-header { display: flex; align-items: center; }
.btn-icon:hover { background: #00ff7f !important; color: black !important; }
</style>

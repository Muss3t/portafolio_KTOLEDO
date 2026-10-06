<template>
  <article class="bento-item hero-profile" style="grid-column: span 2; display: flex; flex-direction: column; gap: 25px; background: rgba(26, 26, 36, 0.98); padding: 30px;">

    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2.5rem; align-items: start;">
      <!-- Izquierda: Perfil y Evolución Académica -->
      <div>
        <div class="hero-header" style="display: flex; align-items: center;">
          <div class="hero-avatar" style="width: 85px; height: 85px; min-width: 85px; border-radius: 50%; overflow: hidden; border: 2px solid #00ff7f;">
            <img src="/img/perfil.png" alt="Kisi Toledo" style="width: 100%; height: 100%; object-fit: cover;">
          </div>
          <div class="hero-titles" style="margin-left: 15px;">
            <h2 style="font-size: 1.4rem; margin: 0; color: #fff;">Kisi Toledo</h2>
            <p class="hero-subtitle" style="font-size: 0.85rem; color: #00ff7f; margin: 4px 0;">
              <i class="ph ph-code"></i> Diseñadora Industrial & UX/UI. Trainee Front-End.
            </p>
          </div>
        </div>

        <div class="hero-links" style="display: flex; flex-wrap: wrap; gap: 10px; font-size: 0.8rem; margin-top: 15px;">
          <span class="hero-link-item"><i class="ph ph-map-pin"></i> Curanilahue</span>
          <a href="mailto:kisitoledom@gmail.com" class="hero-link-item"><i class="ph ph-envelope"></i> Correo</a>
          <a href="https://www.linkedin.com/in/kisitoledo/?isSelfProfile=true" target="_blank" class="hero-link-item"><i class="ph ph-linkedin-logo"></i> LinkedIn</a>
          <a href="https://github.com/Muss3t" target="_blank" class="hero-link-item"><i class="ph ph-github-logo"></i> GitHub</a>
        </div>

        <!-- Evolución Académica (Lista desglosada para lucir el CV) -->
        <div class="evolucion-section" style="margin-top: 25px;">
          <h3 style="color: #00ff7f; font-size: 0.95rem; margin-bottom: 10px;"><i class="ph ph-graduation-cap"></i> EVOLUCIÓN ACADÉMICA</h3>

          <!-- Contenedor con altura máxima y scroll -->
          <div class="estudios-lista custom-scroll" style="display: flex; flex-direction: column; gap: 8px; max-height: 180px; overflow-y: auto; padding-right: 10px;">

            <div class="estudio-item" style="background: rgba(0, 255, 127, 0.05); padding: 10px 14px; border-radius: 6px; border-left: 3px solid #00ff7f; flex-shrink: 0;">
              <h4 style="color: #fff; font-size: 0.85rem; margin: 0;">Desarrollo Front-End Trainee</h4>
              <p style="color: #a0a0b0; font-size: 0.75rem; margin: 2px 0 0 0;">Bootcamp 441 hrs [Actual]</p>
            </div>

            <div class="estudio-item" style="background: rgba(255, 255, 255, 0.03); padding: 10px 14px; border-radius: 6px; flex-shrink: 0;">
              <h4 style="color: #fff; font-size: 0.85rem; margin: 0;">Certificación UX/UI Design</h4>
              <p style="color: #a0a0b0; font-size: 0.75rem; margin: 2px 0 0 0;">Universidad Andrés Bello [2024 - 2025]</p>
            </div>

            <div class="estudio-item" style="background: rgba(255, 255, 255, 0.03); padding: 10px 14px; border-radius: 6px; flex-shrink: 0;">
              <h4 style="color: #fff; font-size: 0.85rem; margin: 0;">Diplomado en Diseño Web</h4>
              <p style="color: #a0a0b0; font-size: 0.75rem; margin: 2px 0 0 0;">Especialización Profesional [2024 - 2025]</p>
            </div>

            <div class="estudio-item" style="background: rgba(255, 255, 255, 0.03); padding: 10px 14px; border-radius: 6px; flex-shrink: 0;">
              <h4 style="color: #fff; font-size: 0.85rem; margin: 0;">Diplomado en Marketing Digital</h4>
              <p style="color: #a0a0b0; font-size: 0.75rem; margin: 2px 0 0 0;">Especialización Profesional [2024 - 2025]</p>
            </div>

            <div class="estudio-item" style="background: rgba(255, 255, 255, 0.03); padding: 10px 14px; border-radius: 6px; flex-shrink: 0;">
              <h4 style="color: #fff; font-size: 0.85rem; margin: 0;">Diplomado en Gestión Ágil de Proyectos</h4>
              <p style="color: #a0a0b0; font-size: 0.75rem; margin: 2px 0 0 0;">Metodologías Ágiles [2024 - 2025]</p>
            </div>

            <div class="estudio-item" style="background: rgba(255, 255, 255, 0.03); padding: 10px 14px; border-radius: 6px; flex-shrink: 0;">
              <h4 style="color: #fff; font-size: 0.85rem; margin: 0;">Diseñadora Industrial</h4>
              <p style="color: #00ff7f; font-size: 0.75rem; margin: 2px 0 0 0;">Universidad del Bío-Bío [2016]<br><em>Premio: Mejor Proyecto de Título de la Generación</em></p>
            </div>

          </div>
        </div>
      </div>

      <!-- Derecha: Sobre Mí -->
      <div style="border-left: 1px solid rgba(255,255,255,0.08); padding-left: 25px;">
        <div class="status-indicator" style="font-size: 0.7rem; margin-bottom: 6px;"><span></span> WHO AM I</div>
        <h3 style="color: #00ff7f; font-size: 1rem; margin-bottom: 8px;"><i class="ph ph-user"></i> Sobre Mí</h3>
        <p style="font-size: 0.85rem; color: #d0d0d8; line-height: 1.6; margin: 0 0 15px 0;">
          Soy Kisi Toledo Muñoz, una profesional que transita constantemente entre el mundo físico y el digital. Mi base como Diseñadora Industrial me enseñó a entender cómo las personas interactúan con los objetos, y hoy aplico esa misma lógica sistémica al desarrollo Front-End y al diseño UX/UI.
        </p>
        <p style="font-size: 0.85rem; color: #a0a0b0; line-height: 1.6; margin: 0;">
          Cuando apago el computador, mis manos siguen ocupadas: disfruto mucho la música y me relajo tocando el <strong>bajo eléctrico</strong>. También soy fanática de la ilustración y el Pop Art. Todo esto lo hago desde mi base en Curanilahue, en compañía de mis gatos.
        </p>
      </div>
    </div>

    <!-- Carrusel -->
    <div class="carrusel-integrado" style="background: rgba(0,0,0,0.3); padding: 15px; border-radius: 10px; border: 1px solid rgba(255,255,255,0.06);">
      <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 10px;">
        <h4 style="color: #00ff7f; font-size: 0.9rem; margin: 0;"><i class="ph ph-images"></i> Galería de Proyectos 3D & Pop Art</h4>
      </div>

      <div class="carrusel-wrapper" style="text-align: center;">
        <div style="width: 100%; height: 220px; display: flex; justify-content: center; align-items: center; margin-bottom: 10px; background: rgba(0,0,0,0.5); border-radius: 8px;">
          <img :src="'/img/' + proyectos[slideActual].img" :alt="proyectos[slideActual].titulo" style="max-width: 100%; max-height: 100%; object-fit: contain; border-radius: 6px;">
        </div>
        <h5 style="color: #fff; font-size: 0.9rem; margin: 4px 0;">{{ proyectos[slideActual].titulo }}</h5>
        <div class="carrusel-controles" style="display: flex; justify-content: center; gap: 15px; margin-top: 10px;">
          <button @click="prev" class="btn-icon" style="background: rgba(255,255,255,0.1); padding: 5px 14px; border-radius: 12px; font-size: 0.8rem; color: white; border: none; cursor: pointer;"><i class="ph ph-arrow-left"></i> Anterior</button>
          <span style="font-size: 0.85rem; color: #00ff7f; align-self: center; font-weight: bold;">{{ slideActual + 1 }} / {{ proyectos.length }}</span>
          <button @click="next" class="btn-icon" style="background: rgba(255,255,255,0.1); padding: 5px 14px; border-radius: 12px; font-size: 0.8rem; color: white; border: none; cursor: pointer;">Siguiente <i class="ph ph-arrow-right"></i></button>
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
  { titulo: 'Helicóptero', desc: 'Diseño e Impresión 3D', img: 'helicoptero.png' },
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
.btn-icon:hover { background: #00ff7f !important; color: black !important; }
/* Estilos para que el scroll se vea futurista y no rompa el diseño */
.custom-scroll::-webkit-scrollbar { width: 6px; }
.custom-scroll::-webkit-scrollbar-track { background: rgba(255,255,255,0.05); border-radius: 4px; }
.custom-scroll::-webkit-scrollbar-thumb { background: rgba(0,255,127,0.3); border-radius: 4px; }
.custom-scroll::-webkit-scrollbar-thumb:hover { background: #00ff7f; }
</style>

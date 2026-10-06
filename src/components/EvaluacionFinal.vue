<template>
  <article class="bento-item evaluacion-card" style="grid-column: span 1; background: linear-gradient(145deg, rgba(0,255,127,0.05) 0%, rgba(26,26,36,0.95) 100%); padding: 30px; display: flex; flex-direction: column; justify-content: center; align-items: center; border: 2px dashed rgba(0,255,127,0.4); text-align: center; cursor: pointer; transition: all 0.3s;" @click="abrirDrive">
    <!-- Ícono con efecto de pulso -->
    <div class="icon-pulse" style="background: rgba(0,255,127,0.15); width: 80px; height: 80px; border-radius: 50%; display: flex; justify-content: center; align-items: center; margin-bottom: 20px;">
      <i class="ph ph-google-drive-logo" style="font-size: 3rem; color: #00ff7f;"></i>
    </div>
    <h3 style="color: #fff; font-size: 1.3rem; margin: 0 0 10px 0;">Evaluación Final</h3>
    <p style="color: #a0a0b0; font-size: 0.9rem; margin: 0 0 25px 0; line-height: 1.4;">Documento Oficial del Módulo 8.<br>Diseño y Desarrollo de Portafolio.</p>
    <a href="https://docs.google.com/document/d/1FMp6tGKel7FeplkxeFRckVtqOkff8G4hW-zF8j_1HKk/edit?usp=sharing" target="_blank" class="btn-drive" style="background: #00ff7f; color: #000; padding: 14px 30px; border-radius: 30px; text-decoration: none; font-weight: bold; font-size: 1rem; display: flex; align-items: center; gap: 8px; transition: background 0.3s;">
      Ver Documento <i class="ph ph-arrow-up-right"></i>
    </a>

  </article>
</template>

<script setup>
const abrirDrive = () => {
  window.open('https://docs.google.com/document/d/1FMp6tGKel7FeplkxeFRckVtqOkff8G4hW-zF8j_1HKk/edit?usp=sharing', '_blank')
}
</script>

<style scoped>
.evaluacion-card:hover { border-color: #00ff7f; transform: translateY(-5px); box-shadow: 0 10px 30px rgba(0,255,127,0.1); }
.icon-pulse { animation: pulse 2s infinite; }
@keyframes pulse {
  0% { box-shadow: 0 0 0 0 rgba(0,255,127,0.4); }
  70% { box-shadow: 0 0 0 15px rgba(0,255,127,0); }
  100% { box-shadow: 0 0 0 0 rgba(0,255,127,0); }
}
.btn-drive:hover { background: #fff; }
</style>

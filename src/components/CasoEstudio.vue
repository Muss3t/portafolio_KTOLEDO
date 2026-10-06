<template>
  <article class="bento-item foda-card" style="grid-column: span 2; background: rgba(26, 26, 36, 0.98); padding: 30px; display: flex; flex-direction: column;">
    <div style="margin-bottom: 20px;">
      <div class="status-indicator" style="font-size: 0.7rem; margin-bottom: 8px;"><span></span> ANÁLISIS ESTRATÉGICO</div>
      <h3 style="color: #00ff7f; font-size: 1.2rem; margin: 0;"><i class="ph ph-target"></i> Análisis FODA Profesional</h3>
    </div>

    <!-- Grilla de 4 columnas para que se estire a lo ancho -->
    <div class="foda-grid" style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 15px; flex-grow: 1;">
      <div style="background: rgba(0, 255, 127, 0.05); border-left: 3px solid #00ff7f; padding: 15px; border-radius: 6px;">
        <h4 style="color: #00ff7f; margin: 0 0 10px 0; font-size: 0.9rem;"><i class="ph ph-lightning"></i> Fortalezas</h4>
        <ul style="color: #d0d0d8; font-size: 0.8rem; padding-left: 18px; margin: 0; line-height: 1.5;">
          <li>Visión sistémica del Diseño Industrial aplicada al código.</li>
          <li>Sólido manejo de UX/UI y diseño centrado en el usuario.</li>
          <li>Especialización en diseño inclusivo y accesibilidad.</li>
        </ul>
      </div>
      <div style="background: rgba(0, 191, 255, 0.05); border-left: 3px solid #00bfff; padding: 15px; border-radius: 6px;">
        <h4 style="color: #00bfff; margin: 0 0 10px 0; font-size: 0.9rem;"><i class="ph ph-rocket"></i> Oportunidades</h4>
        <ul style="color: #d0d0d8; font-size: 0.8rem; padding-left: 18px; margin: 0; line-height: 1.5;">
          <li>Alta demanda de perfiles híbridos (Diseño + Desarrollo).</li>
          <li>Necesidad creciente de soluciones digitales accesibles.</li>
          <li>Integración de interfaces web con fabricación 3D.</li>
        </ul>
      </div>
      <div style="background: rgba(255, 165, 0, 0.05); border-left: 3px solid #ffa500; padding: 15px; border-radius: 6px;">
        <h4 style="color: #ffa500; margin: 0 0 10px 0; font-size: 0.9rem;"><i class="ph ph-warning-circle"></i> Debilidades</h4>
        <ul style="color: #d0d0d8; font-size: 0.8rem; padding-left: 18px; margin: 0; line-height: 1.5;">
          <li>Nivel Trainee en frameworks Front-End avanzados.</li>
          <li>Curva de aprendizaje técnico frente a perfiles informáticos.</li>
        </ul>
      </div>
      <div style="background: rgba(255, 69, 0, 0.05); border-left: 3px solid #ff4500; padding: 15px; border-radius: 6px;">
        <h4 style="color: #ff4500; margin: 0 0 10px 0; font-size: 0.9rem;"><i class="ph ph-shield-warning"></i> Amenazas</h4>
        <ul style="color: #d0d0d8; font-size: 0.8rem; padding-left: 18px; margin: 0; line-height: 1.5;">
          <li>Avance acelerado de nuevas tecnologías web.</li>
          <li>Alta competitividad en el mercado laboral para Trainees.</li>
        </ul>
      </div>
    </div>
  </article>
</template>

<script setup></script>

<style scoped>
@media (max-width: 768px) {
  .foda-grid { grid-template-columns: 1fr !important; }
}
</style>

<template>
  <article class="bento-item tech-app" id="modulo-asistencia">
    <div class="asistencia-layout">
      <!-- Lado Izquierdo: Controles -->
      <div class="asistencia-controls">
        <div class="vrifik-header">
          <div class="status-indicator"><span></span> SAAS DEVELOPED</div>
        </div>

        <h3>V-RIFIK ASISTENCIA</h3>
        <p>App desarrollada para registro ágil en OTECs y ONGs.</p>
        <p>Diseño UX/UI propio</p>
        <p><strong>Regalo:</strong> Usa esta terminal funcional para pasar tu asistencia y al finalizar sólo copiala!</p>

        <div class="app-interface column-interface">
          <input type="text" id="asistencia-input" placeholder="Nombre del participante..." autocomplete="off">
          <button id="btn-registrar" class="btn-demo">
            <i class="ph ph-plus-circle"></i> MARCA ASISTENCIA
          </button>
        </div>

        <button id="btn-ver-specs" class="btn-code" style="margin-top: 15px;">
          <i class="ph ph-blueprint"></i> Ver Proceso UX/UI
        </button>
      </div>

      <!-- Lado Derecho: Datos -->
      <div class="asistencia-data">
        <div class="list-header">
          <span id="contador-asistencia">0 presentes</span>
          <div class="list-actions">
            <button id="btn-copiar" class="btn-icon" title="Copiar lista"><i class="ph ph-copy"></i> Copiar</button>
            <button id="btn-limpiar" class="btn-icon" title="Borrar lista"><i class="ph ph-trash"></i></button>
          </div>
        </div>
        <ul id="lista-asistencia" class="data-list large-list"></ul>
      </div>
    </div>
  </article>
</template>

<script setup>
</script>

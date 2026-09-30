<template>
  <article class="bento-item tech-app" id="modulo-asistencia" style="background: #1a1a24;">
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

        <div class="column-interface">
          <input
            type="text"
            v-model="nuevoNombre"
            @keyup.enter="registrarAsistencia"
            placeholder="Nombre del participante..."
            autocomplete="off"
            class="vrifik-input"
          >
          <button @click="registrarAsistencia" class="btn-demo">
            <i class="ph ph-plus-circle"></i> MARCA ASISTENCIA
          </button>
        </div>

        <!-- Botón para ver el diseño UX/UI en otra pestaña -->
        <button @click="verProcesoUX" class="btn-code" style="margin-top: 15px;">
          <i class="ph ph-blueprint"></i> Ver Proceso UX/UI
        </button>
      </div>

      <!-- Lado Derecho: Datos -->
      <div class="asistencia-data">
        <div class="list-header">
          <span>{{ asistentes.length }} presentes</span>
                    <div class="list-actions">
            <button @click="copiarLista" class="btn-icon" title="Copiar lista"><i class="ph ph-copy"></i> Copiar</button>
            <button @click="limpiarLista" class="btn-icon" title="Borrar lista"><i class="ph ph-trash"></i></button>
          </div>
        </div>

        <ul class="data-list large-list">
          <li v-for="(persona, index) in asistentes" :key="index">
            <span>{{ index + 1 }}. {{ persona }}</span>
            <button @click="borrarPersona(index)" class="btn-icon btn-delete"><i class="ph ph-x"></i></button>
          </li>
        </ul>
      </div>
    </div>
  </article>
</template>

<script setup>
import { ref, watch, onMounted } from 'vue'

const nuevoNombre = ref('')
const asistentes = ref([])

// Recuperar datos de localStorage al montar el componente
onMounted(() => {
  const datosGuardados = localStorage.getItem('vrifik_memoria')
  if (datosGuardados) {
    asistentes.value = JSON.parse(datosGuardados)
  }
})

// Guardar automáticamente cada vez que cambie la lista
watch(asistentes, (nuevaLista) => {
  localStorage.setItem('vrifik_memoria', JSON.stringify(nuevaLista))
}, { deep: true })

const registrarAsistencia = () => {
  if (nuevoNombre.value.trim() !== '') {
    asistentes.value.push(nuevoNombre.value.trim())
    nuevoNombre.value = ''
  }
}

const borrarPersona = (index) => {
  asistentes.value.splice(index, 1)
}

const limpiarLista = () => {
  if (confirm('¿Seguro que deseas borrar toda la lista?')) {
    asistentes.value = []
  }
}

const copiarLista = async () => {
  if (asistentes.value.length === 0) return
  const textoFormateado = asistentes.value.join('\n')
  try {
    await navigator.clipboard.writeText(textoFormateado)
    alert('¡Lista copiada al portapapeles!')
  } catch (err) {
    console.error('Error al copiar: ', err)
  }
}

// Función que abre la imagen en una pestaña nueva
const verProcesoUX = () => {
  window.open('/img/vrifik-ui.png', '_blank')
}
</script>

<style scoped>
.asistencia-layout { display: grid; grid-template-columns: 1fr 1fr; gap: 2rem; height: 100%; }
.asistencia-controls { display: flex; flex-direction: column; justify-content: flex-start; }
.vrifik-header { display: flex; justify-content: space-between; align-items: flex-start; margin-bottom: 10px; }

.column-interface { display: flex; flex-direction: column; gap: 10px; margin-top: 20px; }
.vrifik-input { width: 100%; padding: 10px; background-color: rgba(0,0,0,0.3); border: 1px solid rgba(255,255,255,0.2); border-radius: 6px; color: white; outline: none; font-family: inherit; }
.vrifik-input:focus { border-color: #00ff7f; }

.asistencia-data { display: flex; flex-direction: column; background: rgba(255, 255, 255, 0.03); backdrop-filter: blur(8px); -webkit-backdrop-filter: blur(8px); border-radius: 12px; padding: 15px; border: 1px solid rgba(255, 255, 255, 0.05); }
.list-header { display: flex; justify-content: space-between; align-items: center; margin-bottom: 10px; font-size: 0.75rem; color: #a0a0b0; font-weight: 600; text-transform: uppercase; }
.list-actions { display: flex; gap: 10px; }

.btn-icon { background: transparent; border: none; color: #a0a0b0; cursor: pointer; font-size: 0.8rem; display: flex; align-items: center; gap: 4px; transition: color 0.3s ease; text-transform: uppercase; }
.btn-icon:hover { color: #00ff7f; }
.btn-delete:hover { color: #ff007f; }

.data-list { list-style: none; overflow-y: auto; margin: 0; padding: 0; }
.large-list { max-height: 260px; flex-grow: 1; }
.data-list li { background: rgba(0, 255, 127, 0.1); color: #00ff7f; padding: 8px 12px; border-radius: 4px; margin-bottom: 5px; font-size: 0.85rem; display: flex; justify-content: space-between; align-items: center; }

@media (max-width: 900px) {
  .asistencia-layout { grid-template-columns: 1fr; }
}
</style>

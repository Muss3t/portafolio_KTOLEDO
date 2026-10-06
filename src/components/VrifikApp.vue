<template>
  <div class="vrifik-widget">
    <!-- Botón Flotante para abrir (Cerrado) -->
    <button v-if="!isOpen" @click="isOpen = true" class="vrifik-fab">
      <i class="ph ph-hand-tap" style="font-size: 1.4rem;"></i>
      <span>¿Pasar asistencia? Prueba V-RIFIK</span>
    </button>

    <!-- Panel de la App (Abierto) -->
    <div v-else class="vrifik-panel">
      <div class="panel-header">
        <div class="status-indicator" style="font-size: 0.65rem;"><span></span> SAAS: V-RIFIK</div>
        <button @click="isOpen = false" class="btn-close"><i class="ph ph-x"></i></button>
      </div>

      <p style="font-size: 0.8rem; color: #a0a0b0; margin-bottom: 15px;">App rápida para registro en OTECs/ONGs. ¡Úsala aquí mismo!</p>

      <div class="vrifik-body">
        <div class="input-group">
          <input
            type="text"
            v-model="nuevoNombre"
            @keyup.enter="registrarAsistencia"
            placeholder="Nombre del participante..."
            class="vrifik-input"
          >
          <button @click="registrarAsistencia" class="btn-add"><i class="ph ph-plus"></i></button>
        </div>

        <div class="list-container">
          <div class="list-header">
            <span>{{ asistentes.length }} presentes</span>
            <div class="actions">
              <button @click="copiarLista" class="btn-copiar"><i class="ph ph-copy"></i> Copiar Lista</button>
              <button @click="limpiarLista" class="btn-text" style="color: #ff4500;"><i class="ph ph-trash"></i></button>
            </div>
          </div>
          <ul class="data-list">
            <li v-for="(persona, index) in asistentes" :key="index">
              <span>{{ index + 1 }}. {{ persona }}</span>
              <button @click="borrarPersona(index)" class="btn-del"><i class="ph ph-x"></i></button>
            </li>
          </ul>
        </div>

        <div class="link-ux"><span @click="verProcesoUX">Ver wireframes de diseño UX/UI</span></div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, watch, onMounted } from 'vue'

const isOpen = ref(false)
const nuevoNombre = ref('')
const asistentes = ref([])

onMounted(() => {
  const datosGuardados = localStorage.getItem('vrifik_memoria')
  if (datosGuardados) {
    asistentes.value = JSON.parse(datosGuardados)
  }
})

watch(asistentes, (nuevaLista) => {
  localStorage.setItem('vrifik_memoria', JSON.stringify(nuevaLista))
}, { deep: true })

const registrarAsistencia = () => {
  if (nuevoNombre.value.trim() !== '') {
    asistentes.value.push(nuevoNombre.value.trim())
    nuevoNombre.value = ''
  }
}
const borrarPersona = (index) => asistentes.value.splice(index, 1)
const limpiarLista = () => {
  if (confirm('¿Borrar lista?')) asistentes.value = []
}
const copiarLista = async () => {
  if (asistentes.value.length === 0) return
  await navigator.clipboard.writeText(asistentes.value.join('\n'))
  alert('¡Lista copiada!')
}
const verProcesoUX = () => window.open('/img/vrifik-ui.png', '_blank')
</script>

<style scoped>
.vrifik-widget { position: fixed; bottom: 30px; right: 30px; z-index: 9999; font-family: sans-serif; }
.vrifik-fab { background: #00ff7f; color: #000; border: none; padding: 14px 24px; border-radius: 50px; display: flex; align-items: center; gap: 10px; font-weight: bold; font-size: 0.9rem; cursor: pointer; box-shadow: 0 4px 20px rgba(0,255,127,0.4); transition: transform 0.2s; }
.vrifik-fab:hover { transform: scale(1.05); }

.vrifik-panel { width: 340px; background: rgba(20, 20, 28, 0.98); border: 1px solid #00ff7f; border-radius: 12px; padding: 20px; box-shadow: 0 10px 40px rgba(0,0,0,0.8); backdrop-filter: blur(10px); display: flex; flex-direction: column; }
.panel-header { display: flex; justify-content: space-between; align-items: center; margin-bottom: 10px; }
.btn-close { background: none; border: none; color: #fff; cursor: pointer; font-size: 1.2rem; }
.btn-close:hover { color: #ff4500; }

.input-group { display: flex; gap: 8px; margin-bottom: 15px; }
.vrifik-input { flex-grow: 1; padding: 10px 12px; background: rgba(0,0,0,0.5); border: 1px solid rgba(255,255,255,0.2); border-radius: 6px; color: white; outline: none; }
.vrifik-input:focus { border-color: #00ff7f; }
.btn-add { background: #00ff7f; color: #000; border: none; padding: 0 14px; border-radius: 6px; cursor: pointer; font-weight: bold; font-size: 1.1rem; }

.list-container { background: rgba(255,255,255,0.03); border-radius: 8px; padding: 12px; }
.list-header { display: flex; justify-content: space-between; align-items: center; font-size: 0.75rem; color: #a0a0b0; margin-bottom: 10px; }
.actions { display: flex; gap: 8px; align-items: center; }

/* NUEVO: Botón COPIAR destacado */
.btn-copiar { background: #00ff7f; color: #000; border: none; padding: 6px 14px; border-radius: 20px; font-weight: bold; font-size: 0.8rem; cursor: pointer; display: flex; align-items: center; gap: 5px; transition: background 0.3s; }
.btn-copiar:hover { background: #00cc66; }
.btn-trash { background: none; border: none; color: #ff4500; cursor: pointer; font-size: 1rem; }
.btn-trash:hover { color: #cc3300; }

.data-list { list-style: none; padding: 0; margin: 0; max-height: 200px; overflow-y: auto; }
.data-list li { background: rgba(0,255,127,0.1); color: #00ff7f; padding: 8px 12px; border-radius: 4px; margin-bottom: 6px; font-size: 0.85rem; display: flex; justify-content: space-between; align-items: center; }
.btn-del { background: none; border: none; color: #a0a0b0; cursor: pointer; }
.btn-del:hover { color: #ff4500; }

/* NUEVO: Enlace UX Sutil */
.link-ux { text-align: center; margin-top: 15px; font-size: 0.75rem; }
.link-ux span { color: #a0a0b0; text-decoration: underline; cursor: pointer; transition: color 0.3s; }
.link-ux span:hover { color: #00ff7f; }
</style>

<template>
  <article class="bento-item caso-estudio" style="grid-column: span 2; position: relative;">
    <div class="status-indicator"><span></span> GALERÍA VISUAL</div>
    <h3 style="color: #00ff7f;"><i class="ph ph-images"></i> Mis Proyectos</h3>
    <div class="carrusel-wrapper" style="margin-top: 15px; text-align: center;">
      <!-- Cuadro de la Imagen -->
      <div class="carrusel-slide">
        <!-- Mientras subes tus fotos a la carpeta public/img/, se verá este cuadro gris de aviso -->
        <div style="width: 100%; height: 220px; background: rgba(0,0,0,0.4); border-radius: 8px; display: flex; align-items: center; justify-content: center; margin-bottom: 10px; border: 1px dashed #00ff7f;">
           <span style="font-size: 0.8rem; color: #a0a0b0;">Sube tu foto a: public/img/{{ proyectos[slideActual].img }}</span>
           <!-- Cuando tengas las fotos, borra el div de arriba y descomenta la etiqueta <img> de abajo -->
           <!-- <img :src="'/img/' + proyectos[slideActual].img" :alt="proyectos[slideActual].titulo" style="width: 100%; height: 100%; object-fit: cover; border-radius: 8px;"> -->
        </div>
        <h4 style="color: #fff;">{{ proyectos[slideActual].titulo }}</h4>
        <p style="font-size: 0.85rem; color: #a0a0b0;">{{ proyectos[slideActual].desc }}</p>
      </div>

      <!-- Controles de Navegación -->
      <div class="carrusel-controles" style="display: flex; justify-content: center; gap: 20px; margin-top: 15px;">
        <button @click="prev" class="btn-icon" style="background: rgba(255,255,255,0.1); padding: 5px 15px; border-radius: 20px;"><i class="ph ph-arrow-left"></i> Anterior</button>
        <span style="font-size: 0.85rem; color: #00ff7f; align-self: center;">{{ slideActual + 1 }} / {{ proyectos.length }}</span>
        <button @click="next" class="btn-icon" style="background: rgba(255,255,255,0.1); padding: 5px 15px; border-radius: 20px;">Siguiente <i class="ph ph-arrow-right"></i></button>
      </div>
    </div>
  </article>
</template>

<script setup>
import { ref } from 'vue'

const slideActual = ref(0)

// Lista de tus proyectos. Solo asegúrate de guardar las fotos con estos nombres en public/img/
const proyectos = ref([
  { titulo: 'Alke Wallet', desc: 'Módulo 5 - Interacciones y DOM', img: 'alke-wallet.jpg' },
  { titulo: 'SmartBudget', desc: 'Módulo 3 - HTML/CSS', img: 'smartbudget.jpg' },
  { titulo: 'Calculadora', desc: 'Módulo 4 - JavaScript Vanilla', img: 'calculadora.jpg' },
  { titulo: 'Taskflow', desc: 'Aplicación de Gestión de Tareas', img: 'taskflow.jpg' },
  { titulo: 'Booklist SPA', desc: 'Vue.js & Componentes', img: 'booklist.jpg' }
])

const next = () => {
  slideActual.value = (slideActual.value + 1) % proyectos.value.length
}

const prev = () => {
  slideActual.value = (slideActual.value - 1 + proyectos.value.length) % proyectos.value.length
}
</script>

<style scoped>
.btn-icon { color: white; border: none; cursor: pointer; transition: all 0.3s; }
.btn-icon:hover { background: #00ff7f !important; color: black; }
</style>

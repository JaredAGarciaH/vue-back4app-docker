<script setup>
const technologies = ['Vue 3', 'Vite', 'JavaScript']
</script>

<template>
  <main class="app-shell">
    <section class="intro">
      <p class="eyebrow">Etapa 1</p>
      <h1>vue-back4app-docker</h1>
      <p>
        Proyecto base creado con Vue 3 y Vite. En esta etapa aun no se conecta
        Back4App, no se implementa CRUD y no se agrega Docker.
      </p>

      <ul aria-label="Tecnologias iniciales">
        <li v-for="technology in technologies" :key="technology">
          {{ technology }}
        </li>
      </ul>
    </section>
  </main>
</template>

<style scoped>
.app-shell {
  display: grid;
  min-height: 100vh;
  place-items: center;
  padding: 2rem;
  background: #f7f7fb;
  color: #1f2937;
  font-family:
    Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI",
    sans-serif;
}

.intro {
  width: min(100%, 680px);
}

.eyebrow {
  margin: 0 0 0.75rem;
  color: #2563eb;
  font-size: 0.875rem;
  font-weight: 700;
  text-transform: uppercase;
}

h1 {
  margin: 0;
  font-size: clamp(2rem, 8vw, 4rem);
  line-height: 1;
}

p {
  margin: 1.5rem 0;
  max-width: 58ch;
  font-size: 1.125rem;
  line-height: 1.7;
}

ul {
  display: flex;
  flex-wrap: wrap;
  gap: 0.75rem;
  margin: 0;
  padding: 0;
  list-style: none;
}

li {
  border: 1px solid #d1d5db;
  border-radius: 999px;
  padding: 0.5rem 0.875rem;
  background: #ffffff;
  font-weight: 600;
}
</style>


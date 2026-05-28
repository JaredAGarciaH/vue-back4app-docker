# vue-back4app-docker

Aplicacion Vue 3 con Vite basada en el tutorial de Back4App "Como implementar una aplicacion Vue.js".

La app se llama **Unbored** y su objetivo es sugerir actividades para no aburrirse. Usa Vue Router, Axios y una pantalla que consume una API publica de actividades.

Nota: el endpoint original del tutorial, `https://www.boredapi.com/api/activity`, puede no responder actualmente. Por eso esta version usa `https://bored-api.appbrewery.com/random`, una API publica compatible que devuelve actividades y permite mantener una peticion real con Axios.

## Tecnologias iniciales

- Vue 3
- Vite
- JavaScript
- npm
- Vue Router
- Axios
- Sass
- Iconify para Vue

## Estructura principal

- `src/router/index.js`
- `src/views/HomeView.vue`
- `src/views/AboutView.vue`
- `src/assets/main.css`

## Instalacion

```bash
npm install
```

## Ejecucion local

```bash
npm run dev
```

Para generar una version de produccion:

```bash
npm run build
```

## Dockerizando la aplicacion Vue

Construir imagen:

```bash
docker build -t vue-back4app-docker .
```

Ejecutar contenedor:

```bash
docker run -p 8080:80 vue-back4app-docker
```

Probar en navegador:

```text
http://localhost:8080
```

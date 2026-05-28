# Vue Back4App Docker

## Descripción

Aplicación Vue.js basada en el tutorial de Back4App sobre cómo implementar una aplicación Vue y dockerizarla para su despliegue. La app se llama Unbored y permite obtener sugerencias de actividades usando una API pública.

El endpoint original del tutorial, `https://www.boredapi.com/api/activity`, puede no responder actualmente. Por ese motivo, esta versión usa `https://bored-api.appbrewery.com/random`, una API pública compatible que devuelve actividades y permite mantener una petición real con Axios.

## Tecnologías utilizadas

- Vue.js 3
- Vite
- JavaScript
- Vue Router
- Axios
- Sass
- Iconify
- Docker
- Nginx

## Instalación

```bash
npm install
```

## Ejecución local

```bash
npm run dev
```

La aplicación quedará disponible en la URL local que indique Vite, normalmente:

```text
http://localhost:5173
```

## Compilar para producción

```bash
npm run build
```

El resultado se genera en el directorio `dist`.

## Dockerizando la aplicación Vue

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

## Estructura principal

```text
src/
  assets/
    main.css
  router/
    index.js
  views/
    AboutView.vue
    HomeView.vue
  App.vue
  main.js
Dockerfile
.dockerignore
```

## Estado del proyecto

- La app mantiene la temática Unbored.
- Home consume una API pública de actividades con Axios.
- About describe brevemente el propósito de la app.
- La navegación entre Home y About usa Vue Router.
- Dockerfile usa multi-stage build con Node y Nginx.
- No incluye docker-compose.

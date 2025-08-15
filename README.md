# Práctica 4 - Introducción a VUEJS

## Prerequisitos

- Tener instalado NodeJS y NPM

## Pasos

1. Iniciar un proyecto nuevo con Vite

   ```bash
   npm create vite@latest
   ```

2. Elegir el nombre del proyecto y seleccionar el framework Vue
3. Mover los archivos creados a la carpeta principal del repositorio
4. Instalar las dependencias del proyecto

   ```bash
   npm install
   ```

5. Iniciar el servidor de desarrollo

   ```bash
   npm run dev
   ```

6. Iniciarlizar el router

   ```bash
   npm install vue-router@4
   ```

7. Crear un archivo `router.js` en la carpeta `src` y configurar las rutas

   ```javascript
   import { createRouter, createWebHistory } from 'vue-router';

   // Importar las vistas
   import Home from '../views/Home.vue';
   import About from '../views/About.vue';

   const routes = [
     { path: '/', component: Home },
     { path: '/about', component: About },
   ];

   const router = createRouter({
     history: createWebHistory(),
     routes,
   });

   export default router;
   ```

8. Importar el router en `main.js` y añadirlo a la instancia de Vue

   ```javascript
   import { createApp } from 'vue';
   import App from './App.vue';
   import router from './router';

   const app = createApp(App);
   app.use(router);
   app.mount('#app');
   ```

9. Crear las vistas `Home.vue` y `About.vue` en la carpeta `views`

   - `Home.vue`

     ```vue
     <template>
       <div>
         <h1>Home Page</h1>
         <p>Welcome to the home page!</p>
         <router-link to="/about">Go to About</router-link>
       </div>
     </template>

     <script>
     export default {
       name: 'Home',
     };
     </script>
     ```

   - `About.vue`

     ```vue
     <template>
       <div>
         <h1>About Page</h1>
         <p>This is the about page.</p>
         <router-link to="/">Go to Home</router-link>
       </div>
     </template>

     <script>
     export default {
       name: 'About',
     };
     </script>
     ```

10. Probar la aplicación accediendo a las rutas `/` y `/about`

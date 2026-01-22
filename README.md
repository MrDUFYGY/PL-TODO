---

### 2. README del Frontend (Astro)

Guarda este contenido como `README.md` en la raíz de tu proyecto de Astro.

```markdown
# ToDo App - Frontend (Astro)

Interfaz de usuario moderna y rápida construida con **Astro**, enfocada en el rendimiento mediante Server-Side Rendering (SSR) y una experiencia de usuario fluida.

## 🎨 Características

* **Framework:** Astro (Modo SSR/Hybrid).
* **Diseño:** CSS personalizado (Sin frameworks pesados, estilo minimalista).
* **Funcionalidades:**
    * Tablero visual de tareas.
    * Carga inicial desde el servidor (evita parpadeos y problemas iniciales de CORS).
    * Interactividad en cliente (Crear, Completar, Eliminar) con JavaScript vainilla.
    * Filtrado dinámico.
* **Integración:** Consume la API REST .NET.

## 🛠 Requisitos Previos

* Node.js (v18 o superior recomendado).
* NPM.
* Tener la API del Backend en ejecución.

## 🚀 Instalación y Ejecución

1.  **Instalar dependencias:**
    Abre una terminal en la carpeta del proyecto y ejecuta:
    ```bash
    npm install
    ```

2.  **Configurar Endpoint de API:**
    * Abre el archivo `src/pages/index.astro`.
    * Verifica la constante `API_BASE` en el bloque superior (Server Script) y en el bloque `<script>` inferior.
    * *Por defecto:* `https://localhost:44317/api/todo` (Asegúrate de que coincida con tu puerto de Visual Studio).

3.  **Configuración para SSL Local (Solo Desarrollo):**
    * El proyecto incluye `process.env["NODE_TLS_REJECT_UNAUTHORIZED"] = 0;` en el frontmatter de Astro para permitir la conexión con el certificado autofirmado de IIS Express de .NET. **No usar en producción.**

4.  **Iniciar servidor de desarrollo:**
    ```bash
    npm run dev
    ```
    La aplicación estará disponible en `http://localhost:4321`.

## 📂 Estructura del Proyecto

* `src/layouts/Layout.astro`: Estructura base HTML y estilos globales.
* `src/pages/index.astro`: Lógica principal. Contiene:
    * **Server Script (---):** Fetch inicial de datos (SSR).
    * **Template:** Marcado HTML del tablero.
    * **Client Script:** Lógica del DOM para interactuar con la API (POST/PUT/DELETE) sin recargar.

## 🐛 Solución de Problemas Comunes

* **Error CORS al pulsar botones:** Asegúrate de que el Backend tiene instalado y configurado `Microsoft.AspNet.WebApi.Cors` en `WebApiConfig.cs`.
* **Error de conexión en carga inicial:** Verifica que la API .NET esté corriendo y que el puerto en `API_BASE` sea el correcto.
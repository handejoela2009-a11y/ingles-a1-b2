# English Path — A1 → B2

Plataforma de aprendizaje de inglés (A1 a B2) con repetición espaciada, evaluación por competencia y contenido interactivo.

**Funciona 100% sin conexión a internet.** Todo (React incluido) está empaquetado dentro de `index.html` — no depende de ningún servicio externo para funcionar.

## Instalar como app en tu celular o computador

### Opción rápida (sin subir nada a ningún lado)
Descarga este repositorio (botón verde **Code → Download ZIP** en GitHub), descomprímelo y abre `index.html` con doble clic. Ya funciona, sin internet.

### Opción recomendada: publicarlo con un enlace propio (gratis, 5 minutos)

1. Crea un repositorio nuevo en GitHub y sube estos archivos tal cual están (`index.html`, `manifest.json`, `service-worker.js`, la carpeta `icons/`).
2. Entra a **Settings → Pages** en el repositorio.
3. En "Source" elige la rama `main` y la carpeta `/ (root)`. Guarda.
4. En 1-2 minutos GitHub te da un enlace como `https://tu-usuario.github.io/tu-repositorio/`. Esa es tu app, con URL propia.

### Instalarla como app de verdad

Una vez que la abras desde ese enlace (o desde cualquier hosting):

- **Android (Chrome)**: aparece un botón "Instalar app" o "Agregar a pantalla de inicio" en el menú (⋮). Queda como un ícono más, se abre a pantalla completa, sin barra del navegador.
- **iPhone (Safari)**: botón compartir (□↑) → **"Agregar a pantalla de inicio"**.
- **Computador (Chrome/Edge)**: aparece un ícono de instalar (⊕ o pantalla con flecha) en la barra de direcciones, a la derecha. Un clic y queda como aplicación de escritorio independiente.

Después de instalarla una vez, el `service-worker.js` guarda una copia local de toda la app — así que abrirla de nuevo funciona igual con muy poca señal o sin señal.

## Estructura del repositorio

```
index.html          → la aplicación completa (React incluido, sin dependencias externas)
manifest.json        → hace que el navegador la reconozca como app instalable
service-worker.js    → cachea la app para uso sin conexión después de la primera visita
icons/                → íconos de la app (192px, 512px, ícono de iOS, favicon)
```

## Notas técnicas

- El progreso de cada persona (nivel, XP, racha, palabras dominadas) se guarda en el propio navegador/dispositivo (`localStorage`), no en un servidor. Cada dispositivo lleva su propio progreso.
- Si abres `index.html` con doble clic (sin subirlo a ningún hosting), el service worker no se activa — pero no hace falta: la app ya funciona sin internet porque todo está embebido en el archivo. El service worker solo mejora la versión publicada en la web (permite "instalarla" y que cargue instantáneo con mala señal).
- Sin conexión, la síntesis de voz del navegador (usada en los ejercicios de listening) puede no estar disponible en algunos dispositivos — es una función del sistema operativo, no de la app.

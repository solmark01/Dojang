# Dojang · Taekwondo

Aplicación web (PWA) para administrar un dojang de Taekwondo: alumnos, cuotas, asistencia, instructores, gastos, caja y **progreso de cinturones**.

Funciona sin conexión, guarda los datos en el propio teléfono (localStorage) y se puede instalar en la pantalla de inicio.

## Archivos

| Archivo | Para qué sirve |
|---|---|
| `index.html` | Toda la aplicación (interfaz y lógica). |
| `manifest.webmanifest` | Nombre, colores e íconos para instalar como app. |
| `sw.js` | Service worker: permite usar la app sin internet. |
| `clave.js` | Clave pública de licencia (no modificar). |
| `icon-192.png`, `icon-512.png` | Íconos de la app. |

## Cómo publicarla

La app necesita servirse por HTTPS (o `localhost`) para que funcione el modo offline y la instalación. Opciones simples y gratuitas:

1. **GitHub Pages**: subir esta carpeta a un repositorio y activar Pages.
2. **Netlify / Vercel / Cloudflare Pages**: arrastrar la carpeta como sitio estático.
3. **Hosting propio**: subir los archivos a cualquier servidor con HTTPS.

Abrir la URL en el celular y elegir **“Agregar a pantalla de inicio”** (Android/Chrome) o **Compartir → Agregar a inicio** (iPhone/Safari).

> Abrir `index.html` con doble clic también funciona, pero sin service worker (no queda offline) y la instalación no está disponible.

## Uso rápido

1. **Datos → Configurar cinturones**: definir la lista de cinturones (nombre, color, meses y clases mínimas). Se puede agregar, editar, borrar y reordenar.
2. **Alumnos → + Nuevo alumno**: cargar datos, cinturón actual, fecha de ascenso, grados (stripes), etiquetas y fecha de examen.
3. **Progreso**: ver la distribución por cinturón, filtrar, detectar quiénes están listos para rendir y registrar ascensos.
4. **Caja / Clases / Instructores / Gastos**: mismo funcionamiento que la app original.

### Cinturones y progreso

- Cada cinturón tiene **color**, **meses mínimos** y **clases mínimas**.
- El progreso de cada alumno se calcula desde su fecha de ascenso y su asistencia.
- Un alumno aparece como **listo para examen** cuando cumple los meses y las clases mínimas.
- Al **registrar un avance** se guarda el histórico, se actualiza el cinturón y, si se cobra, se crea un ingreso vinculado en **Caja**.
- Las **etiquetas** (por ejemplo “Competidor”, “Juvenil”) sirven para buscar y filtrar alumnos.

## Copias de seguridad

Usar **Datos → Copia de seguridad** para exportar/restaurar toda la información (alumnos, cinturones, caja, etc.). Conviene hacerlo periódicamente: los datos viven solo en el navegador del teléfono.

## Notas

- No hay servidor ni base de datos: todo se guarda localmente.
- Si se borran los datos del navegador o se desinstala la app sin backup, se pierde la información.
- La licencia y el mecanismo de activación se mantienen igual que en la app original.

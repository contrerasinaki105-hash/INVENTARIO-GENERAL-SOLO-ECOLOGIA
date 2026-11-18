# Ecologia — Inventario de hilos

Página web para llevar el inventario de hilo de la bodega: bultos, conos, peso neto y bruto en libras y kilos, con descuento rápido por texto (`8/1 rojo 100 libras`), historial de movimientos, alertas de stock bajo y descarga en Excel.

- **Página:** GitHub Pages (`index.html`)
- **Datos:** Firebase Firestore, que guarda cada cambio en la nube
- **Acceso:** inicio de sesión con Google, solo para los correos autorizados

---

## Configuración (una sola vez)

### 1. Crear el proyecto en Firebase
1. Entra a <https://console.firebase.google.com> y pulsa **Agregar proyecto**. Ponle de nombre `ecologia` (Google Analytics no hace falta).
2. En el menú, ve a **Compilación → Firestore Database → Crear base de datos**. Elige una ubicación cercana (por ejemplo `us-central`) e inicia en **modo de producción**.
3. Ve a **Compilación → Authentication → Comenzar → Google**, actívalo y guarda.

### 2. Pegar la configuración
1. En **Configuración del proyecto** (el engranaje) → **Tus apps**, pulsa el ícono **`</>`** (Web) y registra la app con el nombre `ecologia`.
2. Copia los valores de `firebaseConfig` en el archivo **`firebase-config.js`**, reemplazando los de ejemplo.

### 3. Proteger los datos
1. En **Firestore Database → Reglas**, pega el contenido de **`firestore.rules`**.
2. Cambia `TU_CORREO@gmail.com` por tu correo de Google y pulsa **Publicar**.

### 4. Autorizar el dominio de GitHub
En **Authentication → Configuración → Dominios autorizados**, agrega `contrerasinaki105-hash.github.io`.

### 5. Activar GitHub Pages
En el repositorio de GitHub: **Settings → Pages → Source: Deploy from a branch → Branch: `main` / `(root)`** y guarda. Al minuto la página queda en:
`https://contrerasinaki105-hash.github.io/INVENTARIO-GENERAL-SOLO-ECOLOGIA/`

---

## Uso
- Entra con tu cuenta de Google.
- Si la bodega está vacía, pulsa **cargar la existencia inicial (13 títulos)**, o importa tu Excel desde **Agregar artículos**.
- Descontar: `8/1 rojo 100 libras` y Enter. Sumar: `entrada 12/1 negro 2 bultos 24 conos 300 lb`.
- **Editar** en cada fila sirve para corregir un conteo. La corrección queda anotada como "Ajuste" en Movimientos.

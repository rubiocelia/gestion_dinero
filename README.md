# Mis gastos

App web instalable (PWA) para llevar las cuentas desde el móvil. Los datos se guardan **solo en el dispositivo** (localStorage): no hay servidor ni cuentas, y cada persona que la instala tiene sus propios datos.

## Qué hace

- **Cuatro tipos de movimiento:** gasto, ingreso, ahorro (traspaso a la cuenta de ahorro, no cuenta como gasto) y devolución (un bizum de vuelta, que se resta de su categoría).
- **Categorías editables** (nombre, color, crear y borrar): Oficina, Comidas y cenas fuera, Gasolina, Transporte, Coche, Ocio, Ropa, Salud, Suscripciones y Otros. De ingreso: Sueldo y Otros ingresos.
- **Fijos mensuales** (Sueldo, Cuenta de ahorro, Bono de metro, Claude, Spotify): la app recuerda los pendientes de cada mes y el último importe que usaste.
- **Resumen del mes:** total gastado, comparación con el mes anterior, media diaria, previsión, balance (ingresos − gastos − ahorro) y % de ahorro.
- **Presupuesto** de gastos con lo que puedes gastar al día.
- Gráfico de gastos por día y desglose por categoría.
- Búsqueda y filtros.
- **PIN** opcional de 4 cifras.
- **Copia de seguridad** en JSON (guardar y restaurar) y exportación del mes en CSV.
- Funciona sin conexión y tiene modo oscuro automático.

## Archivos

| Archivo | Para qué sirve |
|---|---|
| `index.html` | Toda la app: HTML, CSS y JavaScript |
| `manifest.webmanifest` | Nombre, colores e iconos para poder instalarla |
| `sw.js` | Service worker: permite usarla sin conexión |
| `icon-192.png`, `icon-512.png`, `apple-touch-icon.png` | Iconos |

## Publicarla en GitHub Pages

1. Crea un repositorio llamado `gastos` en GitHub. Puede ser público: lo que se ve es el código, no tus datos.
2. Sube estos archivos a la raíz del repo.
3. En el repo, entra en **Settings → Pages → Build and deployment**, elige *Deploy from a branch*, la rama `main` y la carpeta `/ (root)`, y pulsa **Save**.
4. En uno o dos minutos estará en `https://TU-USUARIO.github.io/gastos/`.

## Instalarla en el móvil

- **iPhone:** abre el enlace en **Safari**, pulsa el botón Compartir y elige **Añadir a pantalla de inicio**. Conviene instalarla: si se usa solo desde Safari, iOS puede borrar los datos de una web que no se abre en unos días.
- **Android:** abre el enlace en Chrome, ve al menú ⋮ y pulsa **Instalar app** (o «Añadir a pantalla de inicio»).

## Actualizarla

Cada vez que cambies algún archivo, sube la versión en `sw.js` (`gastos-v3` → `gastos-v4`…) y haz push. Los móviles cogerán la versión nueva la próxima vez que abran la app con conexión. Los datos no se tocan.

## Ideas pendientes

- Presupuesto por categoría (por ejemplo, Oficina o Comidas fuera).
- Resumen anual.

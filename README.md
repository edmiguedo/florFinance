# Flor Finance 🌻

Herramienta personal para Flor: ingresos, gastos, presupuestos, metas y gestión de horas freelance. Diseño rosado con girasol, adaptable a escritorio y móvil.

## Archivos

- `index.html`: interfaz, estilos y lógica de la aplicación.
- `hours-excel.js`: genera los reportes Excel de horas y cobro sin dependencias externas.
- `sunflower.png`: girasol de la interfaz.
- `.nojekyll`: permite servir los archivos directamente en GitHub Pages.

## Subir a GitHub

1. Creá un repositorio en tu cuenta de GitHub.
2. Descomprimí este ZIP y subí el contenido de la carpeta `flor-finance-github` a la raíz del repositorio, no la carpeta completa.
3. Confirmá la carga con un commit. No necesitás instalar Node.js ni ejecutar un build.

## Publicar con GitHub Pages

En el repositorio, abrí **Settings → Pages**. En **Build and deployment**, seleccioná **Deploy from a branch**, elegí la rama **main** y la carpeta **/(root)**, y guardá. GitHub mostrará la URL al terminar la publicación. La disponibilidad de Pages en repositorios privados depende del plan.

La versión exportada no incluye el control de acceso del alojamiento anterior. Si publicás con Pages, verificá la visibilidad del sitio según tu configuración y plan.

## Probar localmente

Dentro de la carpeta del proyecto:

```bash
python -m http.server 8000
```

Abrí http://localhost:8000. También podés usar la extensión Live Server de VS Code.

## Datos y traslado

Los registros y tarifas se guardan en `localStorage` del navegador; el código no contiene los datos financieros de Flor. No hay servidor ni sincronización entre dispositivos.

Antes de cambiar de sitio, descargá un respaldo desde **Preferencias → Descargar respaldo** en la versión actual. En la nueva dirección, usá **Importar respaldo**. Los datos no se trasladan automáticamente porque cada dirección tiene su propio almacenamiento.

## Gestión de horas

Configurá Keystone, Qlabs u otros clientes en **Tarifas por proyecto**, con tarifa por hora en USD. Se completa en nuevas actividades; cambiar una tarifa no modifica las horas anteriores.

Al registrar horas, podés marcar **Cargar también como ingreso cobrado en Movimientos**, o usar **Cargar ingreso** en la tabla. Se guarda un único ingreso por actividad y se marca como cobrada. Si después editás las horas, ajustá el ingreso desde Movimientos.

Si la moneda general es ARS, el importe se convierte con la tasa guardada en la actividad. La cotización automática usa **DolarAPI, dólar oficial compra**, no Google. Requiere internet; si falla, podés ingresar una tasa manual. No se revalúan automáticamente los registros anteriores.

Los reportes XLSX respetan los filtros de mes, proyecto, estado y búsqueda. Incluyen horas, tarifas, importes y saldo pendiente, con formato de impresión horizontal.

# Validación del prototipo

Fecha: 23 de septiembre de 2026.

## Actualización Firebase y QR

Firebase CLI instalado localmente, login confirmado y destino `ceramicasantiago-61f9d` seleccionado por el usuario. Build de publicación con lista explícita de archivos públicos y generador QR empaquetado. `npm test` ahora contiene 14 pruebas aprobadas: se agregaron pruebas de ida/vuelta del enlace compartido, compresión de valores por defecto, límites de configuración externa y rechazo de enlaces rotos. La validación física de AR sigue pendiente.

Deploy completado en https://ceramicasantiago-61f9d.web.app. Se verificaron el sitio HTTPS, QR público y reapertura de un enlace de Enchape Importado Marfil Rasguñado con las selecciones correctas y acceso automático al modo «En tu espacio». Se publicaron 8 archivos de aplicación; documentos originales y herramientas locales quedaron fuera.

## Comprobado

- `node --check src/app.js` y `node --check src/geometry.js`: sintaxis válida.
- `npm test`: 10 pruebas aprobadas. Cobertura: correspondencia de esquinas y rectas en homografía; rechazo de cuadriláteros cruzados/degenerados/cóncavos; recorte de piezas cuyo centro queda fuera; no solapamiento y respeto de abertura en los cinco patrones; área neta; política de piezas completas; doce combinaciones de catálogo.
- Navegador local: carga de Three.js, vista 3D, controles y reinicio de vista.
- Enchape importado Marfil: formato 24 × 6 × 1,3 cm y terminación Rasguñado; filtrado de colores por línea.
- Ladrillo ranurado: edición real con teclado de largo a 36 cm y actualización de dimensión visible.
- Foto: carga local de PNG de referencia, confirmación de procesamiento local; montaje con cuatro puntos; movimiento de esquina por teclado.
- Muro: espiga, forma inclinada y abertura central representadas sobre ambiente ilustrativo.
- Exportación GLB: el resultado del muro en espiga con abertura abrió correctamente en model-viewer. Se verificó que el hueco, patrón y remate sobreviven a la conversión de instancias.
- AR no disponible en escritorio: mensaje de compatibilidad y visor 3D alternativo, sin fingir sesión de cámara.
- Vista adaptable a 390 × 844: controles legibles, sin desbordamiento horizontal (scrollWidth = clientWidth).
- Acción PNG: generación de Blob sin error de canvas. El evento de descarga no se recibió en la automatización del navegador integrado; pendiente comprobar el archivo guardado en Chrome/Safari. No se considera una descarga en disco verificada.

La consola mostró una advertencia de múltiples copias de Three.js al cargar model-viewer, que incluye su propio motor. Se carga solo al entrar en AR; no hubo errores de consola en los flujos inspeccionados.

## Pendiente para producción

- Prueba física de cámara, detección de pared, escala métrica y salida/retorno en Android WebXR e iOS Quick Look. La revisión de escritorio no valida AR física ni generación USDZ en iOS.
- Confirmar descarga de PNG/GLB/JSON en los navegadores finales.
- Prueba de plugin y shortcode en WordPress HTTPS real. No se ejecutó PHP ni se modificó el sitio de producción.
- Carga prolongada, fotos grandes y orientación EXIF en dispositivos de memoria limitada.
- Revisión con productos reales, color/material, catálogo de ladrillos y cubicación comercial si se incorpora.
- Revisión de accesibilidad con lector de pantalla y dispositivos táctiles reales.

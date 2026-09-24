# Synthetix · Estudio inteligente

Una versión nueva del escritorio de estudio, construida con código propio a partir de la interfaz visible de la app de Base44.

## Incluye

- Organización por asignaturas, temas, sesiones y apuntes.
- Creación y eliminación de cada elemento.
- Editor de apuntes con organización asistida por IA.
- Exámenes por sesión, tema, rango de temas o biblioteca completa.
- Resultados e historial de exámenes.
- Panel de permisos para aprobar o descartar sugerencias de información adicional.
- Guardado automático en el navegador y descarga de copia de seguridad.

## Ejecutar

Abre \`index.html\` en un navegador o sirve la carpeta como sitio estático. La app guarda el contenido en el almacenamiento local del navegador. Los apuntes no se suben al repositorio.

## Activar la IA

La interfaz funciona también sin servidor de IA; en ese caso usa un formato local para apuntes y un generador de ejemplo para preguntas. Para habilitar respuestas reales:

1. Despliega el repositorio en Vercel.
2. En la configuración del proyecto, añade las variables de entorno \`OPENAI_API_KEY\` y \`OPENAI_MODEL\`.
3. No guardes una clave real en este repositorio ni en el código del navegador.

La función \`api/ai.js\` envía a OpenAI solo el texto que el usuario selecciona al pulsar una acción de IA. El navegador habla con esa función del servidor, que mantiene la clave fuera del cliente. El formato de llamada sigue la guía oficial de Responses API: https://developers.openai.com/api/docs/quickstart

GitHub Pages puede alojar la interfaz estática, pero no ejecuta \`api/ai.js\`; para usar IA real hace falta un alojamiento con funciones de servidor como Vercel.

## Datos

Los datos de estudio se guardan en el navegador del usuario mediante localStorage. El botón «Descargar copia de seguridad» exporta las asignaturas, los apuntes y los exámenes en un archivo JSON. El repositorio contiene el código, no esos datos.


# Diseño: actualización del demo Pensar Popayán para la presentación del viernes 2026-07-17

## Objetivo

Actualizar el demo estático (este repo: `index.html` + `panel.html`) para demostrar los dos requerimientos que Pensar Preuniversitario dio en la reunión del 2026-07-14, sin backend: todo simulado con datos en duro, siguiendo los patrones existentes del demo (`go()`/`show()`, `demoToast`, paleta dorada).

Los cuatro elementos a demostrar (confirmados con Nicolás):

1. 7 materias, cada una con banco propio por profesor ("torre de selección")
2. Preguntas realmente tipo ICFES de formato extenso (énfasis del cliente: **muchas** preguntas largas)
3. Mockup del flujo de IA: subir cuestionario → procesar → preguntas generadas
4. Banco de 600 preguntas con renovación semestral visible

## Lo que NO incluye

- Login real por profesor, persistencia, procesamiento real de PDF, backend de ningún tipo.
- Cambios de arquitectura: se mantienen los dos archivos autocontenidos.
- El producto real (fork de smart-preu-app con Supabase) es un proyecto aparte, posterior a que Pensar apruebe.

## 1. App del estudiante (`index.html`)

### Home: 7 materias

Reemplazar las tarjetas actuales por las 7 materias de Pensar, cada una con el nombre de su profesor (nombres ficticios), materializando la "torre de selección" desde el lado del estudiante:

| Materia | Preguntas/cuestionario | Estado en el demo |
|---|---|---|
| Lectura Crítica | 36 | **Jugable** (6 preguntas extensas) |
| Matemáticas | 36 | **Jugable** (6 preguntas extensas) |
| Sociales y Ciudadanas | 36 | toast "versión completa" |
| Inglés | 40 | toast "versión completa" |
| Biología | 20 | toast "versión completa" |
| Física | 20 | toast "versión completa" |
| Química | 20 | toast "versión completa" |

Los números por materia son los que dio el cliente. La tarjeta de "Simulacro completo" (sábado) se conserva.

### Banco de preguntas jugable: ~12 preguntas de formato extenso

Reestructurar el `BANK` único en bancos por materia (`BANKS = { lc: [...], mat: [...] }`) y parametrizar `startQuiz(materia)`. El flujo de quiz/resultados/revisión existente se reutiliza sin cambios de lógica (ya es genérico sobre el array).

- **Lectura Crítica — 6 preguntas**: cada una con pasaje de 150–250 palabras (formato cuadernillo ICFES real). Competencias variadas: información literal, inferencia, intención del autor, evaluación de contenido, función de expresiones, estructura del texto. Varias preguntas pueden compartir un mismo pasaje (como en la prueba real: un texto, 2-3 preguntas).
- **Matemáticas — 6 preguntas**: enunciados extensos de situación-problema (contexto cotidiano colombiano), 2-3 con gráfica o tabla en **SVG inline** (barras, tabla de datos, plano cartesiano). Sin dependencias externas.
- Cada pregunta conserva la estructura actual: `context`, `text`, `opts` (4), `correct`, `exp`, `tip`. Se elimina la distinción Conceptual/Tipo ICFES (era regla de Smart, no de Pensar): todas son "Tipo ICFES". El chip de fase pasa a mostrar la competencia evaluada.
- UI: el contexto largo necesita presentación cuidada — bloque de pasaje con scroll propio si excede ~40% de la pantalla, tipografía legible. Las gráficas SVG van dentro del bloque de contexto.

### Pantalla del profesor (en index.html)

Se conserva la pantalla "Crear pregunta" actual, con un ajuste: selector de materia arriba con nota "cada profesor solo ve su materia" (coherencia con la torre de selección). Cambio menor.

## 2. Panel del instituto (`panel.html`)

### Banco de preguntas: torre de selección + banco de 600

- Encabezado del banco: **"600 preguntas · Lote 2026-B vigente · Próxima renovación: enero 2027"**.
- Selector "Estás viendo como:" con los 7 profesores/materias. Al cambiar, se filtra la vista del banco (lista de preguntas de esa materia, contador propio). Simula que cada profesor solo accede a su torre.
- Desglose por materia: barras con el tamaño del banco de cada materia (proporcional a 36/36/36/40/20/20/20 escalado al banco de 600) — muestra que escuchamos los números exactos que dieron.
- El formulario de nueva pregunta existente se conserva, con el área ligada al profesor seleccionado.

### Nueva vista: "Cargar con IA"

Nuevo ítem en el sidebar. Flujo simulado con `setTimeout`, sin backend:

1. **Zona de carga**: recuadro punteado "Arrastra tu cuestionario (PDF o Word)" con un botón "Seleccionar archivo". Al hacer clic no abre file picker real: pasa directo al paso 2 con un nombre de archivo ficticio ("Cuadernillo_LC_2026-2.pdf · 48 páginas").
2. **Procesamiento**: barra de progreso animada con mensajes secuenciales: "Leyendo el documento…", "Extrayendo preguntas y opciones…", "Identificando respuestas correctas…", "Generando explicaciones…" (~6-8 segundos total, ritmo presentable en vivo).
3. **Resultado**: "24 preguntas generadas · listas para revisión" + 3 tarjetas de vista previa (pregunta extensa real con sus 4 opciones y la correcta marcada) + botones "Aprobar y agregar al banco" (toast de éxito, contador del banco sube) y "Revisar una por una" (toast "versión completa").

El paso de **revisión humana** aparece explícito en el flujo ("listas para revisión") a propósito: prepara la conversación de que la renovación semestral es un servicio con control de calidad, no magia automática.

### Vistas existentes

- **Resultados / Cuestionarios / Estudiantes / Simulacros**: actualizar copys y cifras para que cuadren con 7 materias (selects de área con las 7, filas de cuestionarios por materia con su n.º de preguntas correcto, área más débil, etc.). Sin cambios estructurales.

## 3. Datos y contenido

- Las ~12 preguntas extensas se redactan nuevas, con calidad ICFES real (pasajes originales, opciones plausibles con distractores típicos, explicación pedagógica y tip). Es la parte más laboriosa del trabajo y la más visible en la presentación.
- Nombres de profesores ficticios pero verosímiles para Popayán.
- Cifras del panel coherentes entre vistas (600 en el banco, lote 2026-B, renovación enero 2027, 208 preguntas por simulacro completo).

## 4. Pendiente de aclarar con el cliente (no bloquea el demo)

- La cuenta "600 preguntas = cuestionarios de 161 preguntas" no cuadra con la suma por materias (208). Confirmar el viernes qué significan los 161.
- Si el flujo de IA será self-serve en el producto real o servicio operado por Nicolás (recomendación: servicio recurrente — instalación + renovación semestral).

## 5. Orden de implementación sugerido

1. Redactar las ~12 preguntas extensas (contenido primero: es lo crítico y lo más lento).
2. `index.html`: home con 7 materias + bancos por materia + UI de contexto largo/SVG.
3. `panel.html`: torre de selección + banco de 600 + desglose por materia.
4. `panel.html`: vista "Cargar con IA" con la animación.
5. Pasada final de coherencia de cifras y copys en todas las vistas + prueba manual completa de ambos flujos en móvil y escritorio.

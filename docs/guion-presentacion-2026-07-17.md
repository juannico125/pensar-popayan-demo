# Guion de presentación — Pensar Preuniversitario

**Viernes 17 de julio de 2026** · Interlocutor: técnico, entiende de software.

---

## 0. Cómo usar este documento

Las secciones 1 a 3 son lo que dices y haces en la reunión: guion literal, clic por clic.

Las secciones 4 a 6 son lo que tienes que *entender* para responder sin dudar. No se leen en la reunión; se estudian antes.

La sección 7 es lo que tienes que salir sabiendo: las preguntas que TÚ haces.

Regla de oro para todo el documento: **el demo es una maqueta, el producto real no existe todavía para Pensar, pero sí existe y está en producción para otro instituto.** Nunca inviertas ese orden ni lo maquilles. Un cliente técnico detecta el humo en dos preguntas, y ahí pierdes la venta. Lo que vendes es criterio y ejecución demostrada, no un producto terminado.

---

## 1. La versión de 30 segundos

> "Esto que les voy a mostrar es una maqueta navegable, no el producto. Todo está en duro: no hay base de datos, no hay backend, si recargan la página se reinicia. La construí así a propósito, para que ustedes vean y toquen exactamente lo que les propongo antes de que nadie invierta un peso en construirlo. La arquitectura real que hay detrás de esta propuesta ya la tengo funcionando en producción en otro instituto de Popayán, sobre Supabase y Cloudflare. Lo que estamos decidiendo hoy no es si la tecnología funciona: es si *este* producto es el que ustedes necesitan."

Esa apertura hace tres cosas: te blinda contra "¿esto ya funciona?", establece que tienes experiencia real, y convierte la reunión en una conversación de producto en vez de una demo de ventas.

---

## 2. El guion — clic por clic

Tiempo total objetivo: **12 a 15 minutos de demo**, el resto conversación. No narres cada pantalla; deja que ellos pregunten.

### Bloque 0 — Apertura (1 minuto)

Di la versión de 30 segundos de arriba. Luego:

> "Lo armé alrededor de los dos requerimientos que me dieron el lunes: las 7 materias con banco por profesor, y las preguntas tipo ICFES de verdad, largas, cargadas con IA desde sus propios cuadernillos. Empecemos por el estudiante."

### Bloque 1 — App del estudiante (5 minutos)

Abre [index.html](../index.html).

**Paso 1 — Pantalla de login.** Se ve la marca Pensar.

> "El estudiante entra con su código de instituto, no con email. Secretaría los administra."

**Paso 2 — Clic en "Ingresar".** Llegas al Home con las 7 torres.

> "Aquí están las 7 torres, cada una con el nombre de su profesor y el número de preguntas que ustedes me dieron: Matemáticas 36, Lectura Crítica 36, Sociales 36, Inglés 40, Biología 20, Física 20, Química 20."

**Paso 3 — Señala la tarjeta de "Simulacro completo · 208 preguntas".**

> "El simulacro completo agrega las 7 y suma 208. Ese número me lo dieron ustedes y quiero volver sobre él al final, porque no me cuadra con otro que me dieron."

**Paso 4 — Clic en "Lectura Crítica".** Deja que el pasaje cargue en pantalla y **cállate tres segundos**. Que lo lean.

**Paso 5 — Cuando alguien reaccione al largo del texto:**

> "Esto es lo que ustedes pidieron y es la parte más difícil de todo el proyecto. No es una pregunta de trivia con cuatro opciones cortas: es un pasaje de 200 palabras y tres preguntas que dependen de él, como en el cuadernillo real. Los distractores son plausibles, no de relleno."

**Paso 6 — Responde dos o tres preguntas, incluida una mal a propósito.**

**Paso 7 — Pantalla de Resultados.**

> "Desglose por competencia, no solo por materia. Saber en qué falló sirve; saber que sacó 4 de 6 no sirve."

**Paso 8 — Clic en "Revisar" sobre la que fallaste.**

> "Aquí está el valor pedagógico real: la explicación de por qué la correcta es correcta *y* por qué la que eligió es un error típico. Esa explicación es contenido, no software. Vuelvo a eso en un minuto."

**Paso 9 — Vuelve al login y clic en "Ver panel del instituto (web)".**

> "Ese es el lado del estudiante. Ahora el de ustedes."

Si te piden ver Matemáticas, muéstrala: tiene gráficas SVG embebidas. Buen momento para decir: *"las gráficas están hechas en SVG dentro del mismo archivo, sin librerías y sin imágenes externas. Eso importa para el estudiante que abre esto en un gama baja con datos."*

### Bloque 2 — Panel del instituto (5 minutos)

Abre [panel.html](../panel.html).

**Paso 1 — Vista "Resultados".** Promedio del grupo, área más débil, quién está en riesgo. Pasada rápida, **no te detengas aquí.**

> "Lo que ve el coordinador todos los días."

**Paso 2 — Clic en "Banco de preguntas".** Señala el encabezado, que dice *600 preguntas · Lote 2026-B vigente · próxima renovación: enero 2027*.

> "Su dinámica circular, hecha explícita en la interfaz."

**Paso 3 — Usa el selector "Estás viendo como:" y cambia de profesor.** Hazlo **dos o tres veces**: es un gesto que vende solo.

> "Esta es la torre de selección. Diana ve Lectura Crítica y solo Lectura Crítica. El campo de área está bloqueado a su torre. Carlos no puede tocarle el banco a ella."

**Paso 4 — Baja a "Distribución del banco por torre".**

> "Las 600 repartidas proporcionalmente según los números que ustedes dieron."

**Paso 5 — Clic en "Cargar con IA"** (tiene el badge NUEVO). Este es el momento fuerte.

**Paso 6 — Clic en "Seleccionar archivo".**

> "Simulo que subo un cuadernillo suyo: 48 páginas, PDF."

**Paso 7 — Deja correr la animación completa, unos 7 segundos. No hables encima.** Los mensajes van pasando solos: leyendo el documento, extrayendo preguntas, identificando respuestas correctas, generando explicaciones.

**Paso 8 — Aparece "24 preguntas generadas · listas para revisión".**

> "Fíjense en la palabra **revisión**. No dice 'listas para publicar'."

**Paso 9 — Señala las tres tarjetas de vista previa.**

> "La IA no se inventa las preguntas: las extrae de *su* cuadernillo, el que ustedes redactaron. Lo que sí genera es la explicación pedagógica, y por eso hay un paso de revisión humana obligatorio. Un modelo de lenguaje puede marcar mal una clave. Si publican una respuesta incorrecta a 300 estudiantes, el daño no es técnico, es reputacional."

**Paso 10 — Clic en "Aprobar y agregar al banco".** El contador sube.

> "Y así entra el lote."

**Paso 11 — Vistas "Cuestionarios" y "Simulacros", rápido.**

> "El resto del panel es gestión: qué está activo, quién presentó, la progresión de puntaje entre simulacros."

### Bloque 3 — Cierre (2 minutos) y la pregunta

> "Antes de hablar de plata: hay un número que no me cuadra y no quiero construir sobre un supuesto. Ustedes me dijeron 600 preguntas renovadas cada 6 meses, y también me dijeron 'cuestionarios que posean 161 preguntas'. Pero la suma de las 7 materias da 208, no 161. ¿Los 161 qué son?"

Cállate y deja que respondan. Esta pregunta hace más por tu credibilidad que toda la demo: demuestra que leíste con cuidado, que piensas en el modelo de datos antes de codear, y que no eres el proveedor que dice "sí señor" a todo y después entrega otra cosa.

---

## 3. Los cuatro botones que NO funcionan

Varios botones del panel muestran un aviso de *"estará disponible en la versión completa"*: exportar reporte, agregar estudiante, programar simulacro, ver lista de inscritos. **Es intencional.** Si lo tocas sin querer o si ellos lo tocan:

> "Ese está desconectado a propósito. Marqué qué es demo y qué no en vez de fingir que todo funciona."

No pidas disculpas. Es una decisión de diseño y se defiende como tal.

---

## 4. Conceptos técnicos — lo que tienes que entender

Esta sección es para ti. Cada concepto viene con qué es, por qué lo elegimos, y la frase de una línea para decirlo en voz alta.

### 4.1 Por qué el demo es HTML estático y en memoria

**Qué es.** [index.html](../index.html) y [panel.html](../panel.html) son dos archivos autocontenidos: el CSS y el JavaScript van adentro, no hay build, no hay `package.json`, no hay servidor. El estado vive en variables de JavaScript. "Guardar" solo incrementa un contador y muestra un aviso. Recargar borra todo. La navegación es un router de juguete que alterna una clase CSS entre secciones.

**Por qué.** Porque un demo de ventas tiene un solo trabajo: que el cliente vea el producto y decida. Meterle Supabase, autenticación y persistencia a una maqueta cuesta días y no cambia ni un pixel de lo que el cliente evalúa. Y si Pensar dice que no, no perdiste nada.

**En una frase:** *"El demo no tiene backend a propósito. Un demo con base de datos me habría costado una semana más y ustedes verían exactamente lo mismo en pantalla."*

### 4.2 El producto real: Supabase, Postgres, RLS

**Qué es Supabase.** Un backend gestionado montado sobre PostgreSQL. Te da la base de datos, autenticación (usuarios, sesiones vía JWT), almacenamiento de archivos y una API REST autogenerada desde el esquema. No es una base propietaria: es Postgres de verdad, y si te vas, te llevas el dump.

**Qué es RLS.** Row Level Security es la pieza clave, y es una característica nativa de Postgres, no de Supabase. Son políticas escritas en SQL que se evalúan **en la base de datos**, fila por fila, en cada consulta. Ejemplo conceptual: *un profesor solo puede leer o modificar las filas de la tabla de preguntas donde la materia esté en la lista de materias que tiene asignadas.*

**Por qué importa para "la torre de selección".** La torre de selección **es** RLS. La diferencia entre implementarla en el frontend y en la base de datos es la diferencia entre una apariencia de seguridad y seguridad real.

Si escondes el selector de materias en el frontend, cualquiera con la consola del navegador abierta puede pedir las preguntas de otra materia. El servidor se las va a entregar, porque nadie le dijo que no.

Con RLS, la política vive en Postgres. Aunque el atacante construya la petición a mano, la base de datos devuelve cero filas. **No hay forma de saltarse la política desde el cliente**, porque el cliente nunca es quien decide.

**En una frase:** *"La torre de selección no la implemento escondiendo botones. Va como política de Row Level Security en Postgres: la base de datos misma se niega a devolverle a Diana las preguntas de Carlos, aunque él arme la petición a mano desde la consola."*

Si te preguntan *"¿y cómo sabe la base de datos quién es Diana?"*: el JWT que Supabase Auth emite al iniciar sesión viaja en cada petición, y la política RLS lee el identificador de usuario de ese token. El token está firmado, no se puede falsificar sin la clave del servidor.

### 4.3 Aislamiento entre clientes — léelo dos veces

**El problema.** Ya tienes a Smart Preuniversitario como cliente activo en Popayán. Pensar es, en la práctica, su competencia directa en la misma ciudad. Si Pensar es técnico, va a preguntar —o va a pensar sin preguntar— *"¿mis datos van a estar en el mismo lugar que los de Smart?"*.

**La respuesta correcta, y además la arquitectura correcta.** Instancia separada: un proyecto de Supabase propio para Pensar, base de datos propia, dominio propio. No multi-tenant con un identificador de inquilino en tablas compartidas.

**Por qué esta decisión y no la otra.** Multi-tenant —todos los institutos en la misma base, separados por un campo y políticas RLS— es más eficiente en costo y mantenimiento cuando tienes 50 clientes. Con dos clientes que compiten entre sí, el cálculo es otro: un solo bug en una política filtra los datos de un instituto al otro. El riesgo no es proporcional al ahorro. Instancias separadas hacen que ese bug sea **imposible por construcción**, no improbable: no hay una consulta, ni mal escrita, que pueda cruzar la frontera, porque son bases de datos distintas.

**En una frase:** *"Pensar va en su propio proyecto de Supabase, su propia base de datos, su propio dominio. No comparte infraestructura con ningún otro instituto. Podría meterlos a todos en la misma base separados por políticas, sería más barato para mí, pero un solo error en una política filtraría datos entre competidores. No vale la pena."*

Esa respuesta es honesta, es la decisión técnicamente correcta, y de paso les dice —sin decirlo— que a Smart le das el mismo trato. Eso genera confianza en vez de sospecha.

**Lo que NO haces:** no menciones a Smart por nombre ni des detalles de su implementación. Si te preguntan directo *"¿tú trabajas con Smart?"*, responde con la verdad y con el límite:

> "Sí. Y por eso mismo cada instituto va en infraestructura separada, y no voy a hablarles de la implementación de ellos como no les hablaría a ellos de la de ustedes."

Esa frase convierte un conflicto de interés aparente en una demostración de profesionalismo.

### 4.4 El pipeline de IA — qué hace realmente

Este es el punto donde un cliente técnico puede intentar pillarte. Entiéndelo bien. El flujo real tiene cuatro pasos.

**Uno: ingesta del PDF.** El cuadernillo entra como documento. Si es un PDF con texto seleccionable, el texto se extrae directo. Si es un escaneo —una foto de una hoja— hace falta OCR o un modelo con visión. Esto importa mucho: pregúntales en qué formato tienen los cuadernillos, porque cambia el trabajo por completo.

**Dos: extracción estructurada.** Aquí se le pide al modelo que devuelva JSON con un esquema fijo: cada pregunta con su área, competencia, contexto, enunciado, las cuatro opciones, el índice de la correcta, la explicación y el tip. No se le pide "sacame las preguntas" en texto libre para después parsear con expresiones regulares: se le impone el esquema y el modelo está obligado a cumplirlo. Eso convierte un problema de parsing frágil en un problema de validación.

**Tres: validación automática.** Antes de que lo vea un humano: ¿tiene exactamente cuatro opciones? ¿el índice de la correcta está entre 0 y 3? ¿hay preguntas duplicadas contra el banco existente? Lo que falla el chequeo no llega a revisión.

**Cuatro: revisión humana.** Un pedagogo, de ellos o tuyo, aprueba lote por lote. **Este paso no es negociable** y es exactamente lo que el demo muestra con "listas para revisión".

**Por qué la revisión humana es obligatoria.** Un modelo de lenguaje puede equivocarse en cuál es la clave correcta, sobre todo en preguntas de inferencia donde dos opciones son defendibles. Si publicas una clave errada, el estudiante estudia mal y el instituto queda mal. El costo de revisar 600 preguntas es una tarde; el costo de una clave mal publicada es un cliente perdido.

**En una frase:** *"La IA no inventa el contenido: extrae las preguntas de los cuadernillos que ustedes ya escribieron y las estructura. Lo único que genera desde cero son las explicaciones pedagógicas. Y por eso hay revisión humana antes de publicar: un modelo puede marcar mal una clave, y una clave errada publicada a 300 estudiantes es un problema de ustedes, no mío."*

**Modelo y costo, para que no te agarren en frío.** El trabajo se haría con Claude Opus 4.8, que cuesta 5 dólares por millón de tokens de entrada y 25 por millón de salida. Para un lote completo de 600 preguntas extensas —los cuadernillos de entrada más las preguntas y explicaciones generadas— el costo en tokens es del orden de **5 a 15 dólares**, es decir entre veinte y sesenta mil pesos, **una vez por semestre**. Es una estimación de orden de magnitud, no una cotización: depende de cuántas páginas tengan los cuadernillos y de si vienen escaneados.

Lo importante de ese número es lo que revela: **la IA no es el costo del servicio.** El costo es tu tiempo de operación y revisión. Si te preguntan por precio, no ancles la conversación en tokens.

### 4.5 Por qué el pipeline es un servicio tuyo y no un botón para ellos

En el demo, "Cargar con IA" se ve como una función que ellos usan solos. En la propuesta real, **es un servicio que tú operas**: ellos te mandan los cuadernillos con antelación, tú corres el pipeline, tú validas, tú entregas el lote cargado.

Hay tres razones, en orden de peso.

**La primera es calidad.** La revisión pedagógica no se delega a un botón. Si un profesor sube un PDF a las 11 de la noche y aprueba sin leer, el problema termina siendo tuyo de todos modos.

**La segunda es costo de construcción.** Un flujo autoservicio real necesita subida de archivos, cola de trabajos en segundo plano, manejo de fallos y reintentos, interfaz de revisión pregunta por pregunta, y control de gasto por usuario. Eso es un producto entero. Se hace en la versión 2, cuando ya sepas que el pipeline funciona con *sus* cuadernillos reales.

**La tercera es modelo de negocio.** Convierte una venta única en un ingreso recurrente semestral, alineado con la dinámica circular que ellos mismos propusieron. Ellos ya piensan en ciclos de 6 meses; el servicio calza con eso.

**En una frase:** *"En la primera versión el cargue con IA lo opero yo: ustedes me mandan los cuadernillos con antelación, yo entrego el lote revisado y cargado. No porque no se pueda automatizar, sino porque el paso que de verdad importa —la revisión pedagógica— no se automatiza, y construir toda la interfaz de revisión antes de saber cómo se comportan sus cuadernillos reales es gastar plata en el orden equivocado."*

### 4.6 Rotación semestral: por qué NO se borran las preguntas viejas

**El problema.** Ellos dijeron "600 preguntas renovadas cada 6 meses". La tentación es leer "renovadas" como "reemplazadas": borrar el banco y meter el nuevo.

**Por qué eso rompe todo.** Los resultados históricos apuntan a preguntas. Si borras la pregunta 347, el resultado del simulacro de mayo queda apuntando a la nada: no puedes mostrarle a un estudiante en qué falló, ni comparar el rendimiento del grupo entre semestres, ni auditar nada.

**La solución.** Cada pregunta lleva un campo de lote y otro de vigencia: lote 2026-B, vigente desde tal fecha, hasta tal otra. Renovar significa marcar el lote viejo como no vigente e insertar el nuevo. Nada se borra. El banco activo es una consulta con filtro; el histórico sigue intacto.

Es el mismo principio detrás del versionado, de los borrados suaves y de los libros contables: **los datos que respaldan un hecho pasado no se mutan.** Se agregan hechos nuevos.

**En una frase:** *"Renovar el banco no es borrar el anterior. Cada pregunta lleva su lote y su vigencia. Si borrara el lote 2026-A, los resultados de los simulacros de este semestre quedarían apuntando a preguntas que ya no existen y ningún estudiante podría revisar en qué falló en mayo."*

### 4.7 Hosting, escala y por qué no es un problema

El frontend son archivos estáticos en Cloudflare Pages. Se sirven desde CDN, cargan rápido incluso con conexión mala, y el plan gratuito cubre este volumen sin despeinarse.

El backend es Supabase. El plan Pro cuesta 25 dólares al mes e incluye backups automáticos con recuperación puntual.

Sobre la escala: hablamos de unos 300 estudiantes, con picos el sábado del simulacro. Para Postgres, 300 usuarios concurrentes respondiendo preguntas es carga trivial, órdenes de magnitud por debajo de donde empieza a sudar. **No prometas números que no has medido**, pero tampoco actúes como si la escala fuera un riesgo. No lo es.

**En una frase:** *"Con 300 estudiantes y picos los sábados, la escala no es el problema técnico de este proyecto. El problema técnico de este proyecto es el contenido."*

### 4.8 Datos personales de menores (Ley 1581) — el punto que te hace ver serio

Los estudiantes de Saber 11 son **menores de edad** en su mayoría. Eso pone el proyecto bajo la Ley 1581 de 2012 (habeas data) y su Decreto reglamentario 1377 de 2013, que tratan los datos de niños y adolescentes con protección reforzada: el tratamiento requiere autorización del representante legal y debe respetar el interés superior del menor.

En la práctica esto significa tres cosas.

La autorización de tratamiento de datos la recoge **el instituto** en la matrícula, no la app. Es responsabilidad de ellos y conviene que lo sepan desde ya.

Del lado técnico: HTTPS en todo, contraseñas hasheadas (Supabase Auth lo hace solo), RLS para que ningún estudiante vea los datos de otro, backups, y borrado de cuenta cuando lo pidan.

Y la app debe guardar el **mínimo** de datos personales necesario. Nombre, código y resultados. No documento de identidad, no dirección, no teléfono, si no hace falta.

**En una frase:** *"Sus estudiantes son menores, así que esto cae bajo la Ley 1581 con protección reforzada. La autorización de tratamiento la tienen que recoger ustedes en la matrícula, no es algo que la app pueda resolver. Del lado mío: mínimo de datos personales, aislamiento por RLS, cifrado en tránsito, backups."*

Este punto lo mencionas **tú**, sin que te pregunten. Es el tipo de cosa que un proveedor mediocre no menciona nunca y que un cliente técnico registra inmediatamente.

### 4.9 El puntaje ICFES — el detalle de dominio que vale oro

**Siete materias no son cinco áreas.** El ICFES evalúa cinco áreas: Lectura Crítica, Matemáticas, Sociales y Ciudadanas, Ciencias Naturales e Inglés. Las 7 torres de Pensar mapean así:

- Lectura Crítica → Lectura Crítica
- Matemáticas → Matemáticas
- Sociales y Ciudadanas → Sociales y Ciudadanas
- Inglés → Inglés
- **Biología + Física + Química → Ciencias Naturales** (las tres se agregan en una sola área)

**El puntaje global** va de 0 a 500 y sale de ponderar las cinco áreas, cada una de 0 a 100: las cuatro primeras pesan 3 y el Inglés pesa 1, sobre 13, escalado por 5.

```
Global = redondear( ((LC×3 + MAT×3 + SOC×3 + CN×3 + ING×1) / 13) × 5 )
```

Verifica la aritmética: con 100 en todo da ((300+300+300+300+100)/13)×5 = (1300/13)×5 = 500. Cuadra exacto.

**Por qué esto importa.** Porque significa que el puntaje global de un simulacro **no es la suma de las 7 materias**: hay que agregar las tres ciencias primero y luego ponderar. Es una regla de negocio real que va en el código, y mencionarla demuestra que conoces el dominio y no solo el framework.

**En una frase:** *"Ojo con un detalle: sus 7 torres son 5 áreas ICFES, porque Biología, Física y Química se agregan en Ciencias Naturales. Y el global de 500 es una suma ponderada: Inglés pesa 1 y las demás 3, sobre 13. Eso es una regla que va en el motor de puntaje del simulacro, no es sumar y ya."*

---

## 5. Preguntas difíciles y cómo responderlas

Estúdiate estas. Son las que duelen.

### "¿Esto ya funciona o es solo un mockup?"

> "Es una maqueta, y lo dije al empezar. Nada de lo que ven persiste. Lo que sí funciona hoy, en producción, es la arquitectura que hay detrás de la propuesta —Supabase, Postgres con RLS, estático en Cloudflare— pero para otro instituto, no para ustedes. Construirles el suyo es el trabajo del que estamos hablando."

### "¿Tú trabajas con [la competencia]?"

> "Sí. Y por eso cada instituto va en infraestructura completamente separada: su propio proyecto, su propia base de datos, su propio dominio. Igual que no les voy a contar cómo está hecho lo de ellos, no les contaría a ellos lo de ustedes."

No lo esquives, no lo adornes. La respuesta directa es la fuerte.

### "¿Esto es lo mismo que ya le hiciste a otro y nos lo estás revendiendo?"

> "El demo sí sale de una base común, y eso es a mi favor: significa que llegué a esta reunión con algo terminado en vez de con diapositivas. El producto de ustedes son 7 torres, banco de 600 con rotación semestral y pipeline de IA sobre sus cuadernillos. Ese producto no existe todavía y lo específico de él es la mayor parte del trabajo."

### "¿La IA se inventa las preguntas?"

> "No. Las extrae de los cuadernillos de ustedes, con un esquema fijo de salida. Lo que sí genera es la explicación pedagógica de cada respuesta. Y por eso hay un paso de revisión humana obligatorio antes de publicar."

### "¿Y si la IA se equivoca en una respuesta?"

> "Se va a equivocar en alguna, por eso el flujo tiene revisión. Además hay validación automática antes: cuatro opciones exactas, índice de correcta en rango, sin duplicados contra el banco. Lo que no pasa el chequeo no llega ni a revisión."

### "¿Podemos subir nosotros mismos los cuestionarios?"

> "En la versión que les propongo, no: el cargue lo opero yo. Es una decisión, no una limitación. La revisión pedagógica es el paso que importa y no lo delego a un botón. Cuando ya sepamos cómo se comportan sus cuadernillos reales, hacer el flujo autoservicio es directo, pero construir toda esa interfaz antes de saberlo es gastar en el orden equivocado."

### "¿Están seguros los datos de nuestros estudiantes?"

Ver el punto 4.8. Contesta en este orden: son menores, aplica la Ley 1581 con protección reforzada, la autorización la recogen ellos en la matrícula, y del lado técnico van RLS, HTTPS, mínimo de datos y backups.

### "¿Qué pasa si mañana te vas o te atropella un bus?"

> "El código queda en un repositorio de ustedes, la base es Postgres estándar y se exporta con un comando, y el hosting está a nombre de ustedes. No hay nada propietario mío en el stack. Si mañana contratan a otro desarrollador, recibe todo y sigue."

Prepárate para esto también por escrito en la propuesta. Un cliente técnico *va* a preguntarlo, y la respuesta correcta cierra ventas.

### "¿Funciona sin internet? ¿En celulares de gama baja?"

> "Sin internet no; necesita conexión para cargar preguntas y guardar respuestas. En gama baja sí: es HTML, CSS y JavaScript, sin frameworks pesados y sin imágenes externas. Las gráficas de matemáticas son SVG en el mismo archivo. Pesa poco y carga rápido con datos móviles."

**No prometas offline.** Eso es una PWA con sincronización y es un proyecto en sí mismo.

### "¿Cuánto se demora?"

No improvises un número en la reunión.

> "Te lo mando en la propuesta con el desglose por fase."

Un número inventado bajo presión es una deuda que pagas tú.

---

## 6. Lo que NO debes decir ni prometer

**No prometas app en Play Store o App Store.** Esto es web. Se puede envolver, pero es otro proyecto: cuentas de desarrollador, revisiones, actualizaciones.

**No prometas que funciona sin internet.** Es una PWA con sincronización offline. Proyecto aparte.

**No digas que "la IA lo hace todo automático".** Contradice tu propio argumento de la revisión humana, y además es falso.

**No des un plazo concreto dicho al aire.** Va en la propuesta escrita, con fases.

**No digas que replicas el puntaje ICFES exacto.** Puedes replicar la fórmula de agregación. El ICFES usa además modelos psicométricos (teoría de respuesta al ítem) para convertir aciertos en puntaje por área. Di "estimado", no "idéntico al ICFES".

**No des números de rendimiento que no mediste.** "300 concurrentes no es problema para Postgres" es defendible. "Aguanta 10.000 usuarios" no lo es si no lo probaste.

Y un consejo de tono: **cuando no sepas algo, dilo.** *"No lo sé, lo verifico y te respondo el lunes."* Un cliente técnico confía más en eso que en una respuesta segura y equivocada. La pena no es no saber; la pena es que te pillen inventando.

---

## 7. Lo que tienes que salir sabiendo

Preguntas que **tú** haces. Anota las respuestas en la reunión.

1. **Los 161 contra los 208.** ¿Qué son los 161? ¿Es el simulacro real? ¿Es por sede? ¿Es un conteo viejo? Esto bloquea el modelo de datos del simulacro.
2. **Formato de los cuadernillos.** ¿PDF con texto o escaneados? ¿Word? ¿Impresos en papel y nada más? Cambia por completo el pipeline —texto directo contra OCR o visión— y por lo tanto el esfuerzo y el costo.
3. **Volumen real de cuadernillos.** Para llegar a 600 preguntas, ¿cuántos documentos me van a mandar? ¿Ya los tienen o los redactan sobre la marcha?
4. **¿Las preguntas ya tienen la explicación escrita, o hay que generarla?** Si ya las tienen, el trabajo del modelo baja mucho. Si no, ese es el valor agregado grande.
5. **Número real de estudiantes y jornadas.** El demo dice 300 y jornadas Sabatino e Intensivo. ¿Cuadra?
6. **¿Los 7 profesores existen y van a usar el panel?** ¿O el coordinador carga todo? Define si el login por profesor es versión 1 o versión 2.
7. **¿Quién revisa los lotes generados: ellos o tú?** Define el alcance del servicio recurrente y su precio.
8. **¿Recogen autorización de tratamiento de datos en la matrícula?** Ver el punto 4.8.
9. **¿Tienen dominio? ¿Quién lo paga y a nombre de quién queda?**
10. **Fecha objetivo.** ¿Para cuándo lo quieren en manos de estudiantes? ¿Está amarrado a algún ciclo?

---

## 8. Checklist técnico — 15 minutos antes

- [ ] Abrir [index.html](../index.html) y [panel.html](../panel.html) y recorrer **los dos flujos completos** una vez. Si algo falla, te enteras tú, no ellos.
- [ ] Verificar que las fuentes de Google cargan, porque necesitan internet. Si no hay internet en el sitio, pruébalo antes en modo avión: se ve distinto sin las fuentes, pero funciona.
- [ ] Correr la animación de "Cargar con IA" una vez, cronometrada. Tienes que saber cuántos segundos vas a estar callado.
- [ ] Zoom del navegador al 100%. Ventana lo bastante ancha para que el panel no colapse a móvil.
- [ ] Cerrar pestañas, notificaciones, Slack, todo. Nada de nombres de otros clientes visibles en pantalla. **Especialmente eso.**
- [ ] Tener este documento abierto en otra ventana o impreso, en la sección 5.
- [ ] Recargar las páginas antes de empezar: el estado se acumula (los contadores del banco suben) si ya jugaste con ellas.

---

## 9. Si tienes que resumirlo todo en tres ideas

**Uno: honestidad sobre el estado.** Es una maqueta y lo dices tú primero. Lo que vendes es criterio demostrado, no un producto terminado.

**Dos: la torre de selección es RLS, no botones escondidos.** Es tu prueba de que piensas en seguridad de verdad, no en apariencias.

**Tres: la IA no es el producto, la revisión humana es el producto.** Ese es el argumento que justifica que sea un servicio recurrente tuyo y no un botón, y de paso te blinda contra el riesgo de una clave mal publicada.

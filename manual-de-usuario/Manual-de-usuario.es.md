<div class="cover">

# NextHelp

## Manual de usuario

Tu copiloto para cualquier reunión · Versión 1.0 · macOS (Apple Silicon)

*by Zeedatik · [zeedatik.com](https://zeedatik.com)*

</div>

<div class="pagebreak"></div>

# 1. Qué es NextHelp

NextHelp es una app para Mac que te acompaña durante una reunión, una clase o una llamada. **Escucha, transcribe, traduce y te sugiere qué responder**, usando la información de tus propios documentos.

Funciona así, de un vistazo:

1. **Escucha** dos fuentes: lo que suena en tu Mac (los demás en la llamada, que la app llama **«Ellos»**) y tu micrófono (**«Tú»**).
2. **Transcribe** en vivo, en tu Mac y sin internet.
3. Cuando alguien te hace una pregunta, pulsas **Responder lo último** y la IA te propone una respuesta, apoyándose en los documentos del **perfil** que elegiste.

> Por defecto, la transcripción y la IA corren en tu Mac. Si tú eliges un proveedor de IA en la nube, el texto que envíes lo procesa ese proveedor.


# 2. Requisitos e instalación

- Mac con **chip Apple (M1 o posterior)**. No hay versión para Mac con Intel.
- **macOS 15 o posterior** (se recomienda macOS 26: mejor transcripción y traducción).
- De 5 a 10 GB libres si quieres modelos de IA locales.

**Instalación en cuatro pasos** (la guía completa está en [INSTALL.md](https://github.com/zeedatik/NextHelp/blob/main/INSTALL.md)):

1. Descarga el `.dmg` de la página de [Releases](https://github.com/zeedatik/NextHelp/releases/latest).
2. Ábrelo y arrastra **NextHelp** a **Aplicaciones**.
3. Abre **Terminal** y ejecuta, una sola vez:

   ```bash
   xattr -dr com.apple.quarantine /Applications/NextHelp.app
   ```

   Esto es necesario porque la app todavía no está notarizada por Apple. Sin este paso, macOS solo ofrece «Mover a la papelera» o «Cerrar» y la app no abre. No la muevas a la papelera.
4. Abre NextHelp desde Aplicaciones.

## Actualizar NextHelp

1. Cierra NextHelp (⌘Q).
2. Abre el `.dmg` nuevo y arrastra **NextHelp** a **Aplicaciones**, reemplazando la app anterior.
3. Ejecuta de nuevo el comando `xattr` de arriba y abre la app.
4. Tus perfiles, documentos y transcripciones se conservan (viven fuera de la app). Si algún perfil aparece como desactualizado, pulsa **Reindexar** (sección 7).
5. macOS puede pedirte los permisos otra vez. Si el audio de «Ellos» no funciona después de actualizar, usa **Configuración → General → Resolver conflicto de permisos** (sección 15).

# 3. Primer arranque

**Términos y privacidad.** La primera vez debes leer y aceptar los Términos de uso y el Aviso de privacidad. Al aceptar, te haces responsable de avisar y obtener el consentimiento de las personas a las que transcribas.

**Permisos de macOS.** La app te pedirá:

| Permiso | Para qué sirve |
|---|---|
| Micrófono | Transcribir lo que dices tú. |
| Reconocimiento de voz | Convertir el audio en texto. |
| Grabación de pantalla y audio del sistema | Oír a los demás en la llamada («Ellos»). |

Si olvidas uno, actívalo en **Ajustes del Sistema → Privacidad y seguridad** y vuelve a abrir la app.

**Asistente de bienvenida.** Revisa tu Mac (memoria y disco libre), recomienda modelos y, si lo aceptas, **instala Ollama** (el programa que ejecuta los modelos locales) y **descarga los modelos recomendados**. No necesitas usar la terminal. Puede tardar varios minutos según tu conexión: espera a que termine antes de tu primera reunión. Si prefieres usar un servicio en la nube, elige **«Prefiero usar un proveedor en la nube»** y agrega tu proveedor (ver sección 12).

Al terminar verás **«Todo listo»**. Más adelante puedes repetir el asistente desde **Configuración → Servicios → Repetir bienvenida**.

# 4. Recorrido por la ventana

![Ventana principal de NextHelp (ilustración con contenido de ejemplo)](img/fig1.png)

La ventana tiene tres zonas: **A) Transcripción** (lo que se dice), **B) Respuestas** (lo que te sugiere la IA) y **C) el campo de aclaración con el botón «Responder lo último»**. Arriba está la barra de botones. Un botón en **azul** significa que esa función está activada.

| N.º | Botón | Qué hace |
|---|---|---|
| 1 | **Perfil** | Elige el grupo de documentos con el que se responde (sección 7). |
| 2 | **Rápido / Razonar** | Rápido responde en pocos segundos. Razonar hace que el modelo piense antes de responder: más preciso, pero puede tardar minutos. |
| 3 | **Configuración** | Modelos, ventana de contexto, voz, proveedores, servicios, perfiles y memoria. |
| 4 | **Nueva reunión** | Guarda la transcripción actual y empieza una reunión nueva (archivo, título y resumen nuevos). |
| 5 | **Transcripciones** | Abre la carpeta donde se guardan las transcripciones de cada reunión. |
| 6 | **Teleprompter** | Muestra u oculta el teleprompter (sección 9). Se quita con este mismo botón. |
| 7 | **Visible / Invisible al compartir** | Si está en «Invisible», esta ventana no se ve cuando compartes pantalla (sección 10). |
| 8 | **Encima de todo** | La ventana flota sobre las demás apps, también en pantalla completa y en todos los escritorios. |
| 9 | **Apariencia** | Transparencia del fondo y del texto, color del texto y modo compacto. |
| 10 | **Traducir** | Traduce en vivo y pone la traducción debajo de cada línea (sección 6). |
| 11 | **Idioma** | Lista de idiomas a los que se traduce («Traducir a»). |
| 12 | **Mis frases** | Traduce también lo que dices tú. Por defecto solo se traduce lo que dicen «Ellos». |
| 13 | **− 80 % +** | Reduce o amplía toda la app: texto, botones y ventana (⌘− y ⌘+). |
| 14 | **Silenciar audio interno** | Deja de transcribir lo que suena en la Mac («Ellos»). |
| 15 | **Mutear mi mic** | Deja de transcribir lo que dices tú. |

Los botones pueden mostrarse solo con su ícono (modo compacto). Pasa el cursor sobre uno para ver su descripción.

**Barra de la reunión.** Junto a los botones anteriores hay cuatro controles para la reunión en curso (detalles en la sección 8):

| Control | Qué hace |
|---|---|
| **Título de la reunión** | Campo para nombrar la reunión. Renombra el archivo del guardado automático. |
| **Resumen** | Genera un resumen corto de la reunión hasta ahora, con decisiones y pendientes. |
| **Guardar como…** | Guarda la transcripción como `.txt`, `.md` o `.json`. |
| **Abrir reciente** | Abre en solo lectura una transcripción guardada. |

**Indicador de datos en la nube.** Si algún proveedor de IA en la nube está activo, aparece un indicador permanente en la barra superior para recordarte que la transcripción y los fragmentos de documentos necesarios salen de tu Mac. Si todo es local, no aparece.

# 5. Transcripción y respuestas

## La transcripción

- Las líneas de **«Ellos»** vienen del audio de tu Mac. Las de **«Tú»**, de tu micrófono.
- Una línea en **cursiva** todavía no está confirmada: espera a que deje de estar en cursiva antes de corregirla.
- Para **corregir** una línea, pulsa su lápiz, edita el texto y confirma con **Enter** (o **Esc** para cancelar). Queda marcada como «Corregido a mano».
- Haz clic en una o varias líneas para **seleccionarlas**. Con **Borrar** las quitas de la transcripción y con **Limpiar** quitas la selección.
- **La transcripción te sigue.** Mientras estás abajo, la vista avanza sola con lo último que se dice. Si subes a leer algo, se queda donde estás y la flecha junto al título «Transcripción» se resalta con el número de líneas nuevas. Púlsala para volver a lo último y seguir.
- Si el audio del sistema se interrumpe (por ejemplo, al desconectar un monitor o al salir de reposo), verás el aviso «Audio del sistema interrumpido, reconectando…» y la app lo reconecta sola.
- Cada reunión se guarda sola en `~/Documents/MeetingAssistant/Transcripciones/` (sección 8). El archivo refleja también tus correcciones y borrados. **Nueva reunión** cierra la actual y empieza otra.

## Pedir una respuesta

| Quiero... | Haz esto |
|---|---|
| Responder la última pregunta de «Ellos» | Pulsa **Responder lo último** o usa **⌘↩**. |
| Responder una parte específica | Selecciona una o varias líneas y pulsa **Responder selección**. Se responde a esas líneas, aunque sean tuyas. |
| Darle contexto a la IA | Escribe una **aclaración opcional** (por ejemplo «se refiere al módulo Change Management»). Sirve para buscar mejor en tus documentos. |
| Hacer una pregunta libre | Escribe abajo en «Pregúntale algo sobre la reunión…». La IA usa el resumen de la reunión, los hechos importantes y lo último que se dijo, además de los documentos del perfil. |
| Una respuesta más razonada | Pulsa **Profundizar** en una tarjeta de respuesta rápida: aparece una tarjeta nueva, etiquetada «razonado», y la primera no cambia. |
| Una versión más desarrollada en el mismo hilo | Pulsa **Detallar**: agrega al mismo hilo una versión con más puntos y ejemplos. |
| Preguntar sobre un hilo concreto | Pulsa **Seleccionado / Preguntar** en ese hilo; lo que escribas abajo se preguntará sobre él. |
| Detener una respuesta | Pulsa **Detener**. |

Cada respuesta indica de qué **fuentes** (documentos) salió. En modo **Razonar** puedes abrir **Ver razonamiento**.

**Cómo responde ⌘↩.** Siempre responde primero en modo **Rápido**, para que veas algo de inmediato. Si tu ajuste es **Razonar**, al terminar la respuesta rápida la app lanza sola la tarjeta razonada debajo.

**Si lo último no es una pregunta.** NextHelp no se queda en blanco: si «Ellos» hacen una afirmación o un pedido, te sugiere qué decir. Si seleccionas algo muy corto como «sí, eso mismo», usa el contexto previo para su mejor suposición y te hace una pregunta corta de aclaración.

**Texto que aparece al instante.** La respuesta empieza a mostrarse en cuanto llega el primer fragmento y se refresca de forma fluida. El botón **Profundizar** se desactiva mientras haya otra respuesta en curso.

# 6. Traducción

La traducción **se hace en tu Mac con el traductor de macOS, sin internet**.

1. Pulsa el botón **Traducir** (10). Se pone en azul y la traducción aparece debajo de cada línea.
2. Para elegir el idioma, abre la lista de idiomas junto al botón (11). Si a un idioma le falta el paquete (⬇︎), macOS te pide permiso para descargarlo **una sola vez**. Un ✓ indica que ya está listo, y «(vía modelo)» que se traducirá con el modelo de IA.
3. Para apagarla, vuelve a pulsar **Traducir**.

**Importante: por defecto solo se traduce lo que dicen «Ellos».** Si quieres ver también la traducción de lo que dices tú, pulsa el botón **Mis frases** (12), junto a la lista de idiomas. Se pone en azul cuando está activo; pulsa otra vez para apagarlo.

Si la traducción va a usar el modelo de IA, se aplaza mientras la IA está respondiendo una pregunta tuya, para que no compitan por la memoria de tu Mac.

Si ves el error «No se pudo traducir», revisa **Ajustes del Sistema → General → Idioma y región → Idiomas de traducción**.

# 7. Perfiles y documentos

## Qué es un perfil

Un **perfil** es un grupo de documentos sobre un tema: por ejemplo tu CV y proyectos, el material de una materia o los manuales de un cliente. Cambias de perfil con el selector **Perfil** (1) y la IA responde con ese material.

| Perfil | Cómo responde |
|---|---|
| **general** | Los documentos solo **apoyan**. Si no hay o no sirven, la IA responde igual, con su propio conocimiento y la transcripción. |
| **Cualquier perfil que crees** | Modo estricto: la IA responde **únicamente con lo que dicen tus documentos** de ese perfil. Si el perfil no tiene documentos, la app te lo avisa. |

![Selector de perfiles (ilustración con perfiles de ejemplo)](img/fig3.png)

## Crear un perfil y agregar documentos

1. Abre **Configuración → Perfiles**.
2. Pulsa **Nuevo perfil** y escribe un nombre. Solo se admiten letras minúsculas sin acentos, números y guion bajo (`_`); lo demás se convierte en `_`. Ejemplos: `mi_cv`, `entrevista_backend`, `fisica_2`.
3. Selecciona el perfil y pulsa **Agregar documentos…**. Puedes elegir varios a la vez.
4. Espera a que termine la indexación (la app muestra el avance y puedes **Cancelar indexación**). Verás cuántos fragmentos tiene cada documento y cuántos quedaron indexados o sin cambios.
5. Cierra Configuración, elige el perfil en el selector y empieza a preguntar.

## Documentos admitidos

| Formato | Notas |
|---|---|
| **`.md` (Markdown)** | **El mejor formato.** Los títulos `#` y `##` se respetan como secciones. |
| **`.txt`** | Texto plano. |
| **`.pdf`** | Debe tener **texto seleccionable**. Se lee por página. |
| **`.docx`** (Word) | Párrafos, estilos de título y tablas sencillas. |
| **`.pptx`** (PowerPoint) | El texto de cada diapositiva. |
| **`.xlsx`** (Excel) | Cada hoja es una sección; cada fila se guarda como `columna: valor`. |
| **`.csv`, `.json`** | Cada fila del CSV como `columna: valor`; el JSON se aplana a `ruta: valor`. |
| `.rtf`, `.doc` (antiguo), `.html` | Solo texto. En HTML se ignoran scripts, estilos y recursos externos. |

**No se admiten (todavía):** PDF escaneado o solo imágenes (necesita OCR), PDF con contraseña, Word o Excel cifrados, imágenes sueltas, audio y video. Si tu PDF es un escaneo, conviértelo antes a PDF con texto o cópialo a un `.md`. Las tablas complejas de un PDF se leen como texto, pero pierden su estructura.

**Límites (por seguridad y rendimiento):** 20 MB por archivo, 500 páginas, diapositivas u hojas, y 1,500 fragmentos por documento. Si algo se pasa, la app te lo dice con un mensaje claro y no indexa basura. Si vuelves a agregar un archivo que no cambió, se salta; si cambió, solo se recalculan los fragmentos modificados.

## Avisos sobre tus documentos

Al indexar, la app revisa cada documento y, en **Configuración → Perfiles → Avisos sobre tus documentos**, te dice cómo mejorarlo. Te avisa si un documento es muy corto (menos de 500 caracteres), no tiene encabezados, es demasiado grande, tiene muchos caracteres ilegibles o repite el nombre de otro documento del mismo perfil.

## Cómo escribir buenos documentos

La app divide cada documento por **secciones y párrafos** y, para cada pregunta, busca los fragmentos más parecidos. Estas reglas ayudan mucho:

1. **Hechos clave al inicio:** precio, para quién es y qué lo diferencia, en las primeras líneas.
2. **Encabezados descriptivos con el nombre del producto o tema** («Precios de NextHelp Pro», no «Precios»).
3. **Secciones que se entiendan solas**, de unas 150 a 350 palabras.
4. **Nombres consistentes:** repite «NextHelp» en lugar de alternar «el asistente» o «la herramienta».
5. **Glosario** de siglas y términos internos.
6. **Preguntas frecuentes** con la pregunta como la diría la otra persona y una respuesta corta.
7. **Evita tablas anchas:** prefiere listas («Plan: Pro; Precio: 20 USD»).
8. **Título, fuente y fecha** al inicio de cada documento.
9. **Un tema por archivo**, mejor que un solo archivo enorme.
10. **Sin relleno:** quita portadas, índices y avisos legales que no aportan respuestas.

Para respuestas **Rápidas** conviene tener fichas cortas (un dato, una cifra, una frase lista para decir). Para **Razonar** sirven secciones más largas, comparativas y argumentos con matices.

En **Configuración → Perfiles** hay un botón **Ver plantilla ideal** con un documento de ejemplo listo para copiar con **Copiar plantilla**. Un ejemplo sencillo para entrevistas:

```markdown
# Ana Pérez — CV

Fuente: mi CV · Fecha: 2026-10-01

## Proyecto: Sistema de reservas
Aplicación web para reservar salas de estudio.
Tecnologías: Python, FastAPI y PostgreSQL.
Mi rol: diseño y desarrollo. Resultado: bajé el tiempo de reserva
de 5 minutos a 30 segundos.

## Proyecto: Tablero de inventario
Tablero para una tienda pequeña, hecho con React y una API REST.
Resultado: lo usan cada día 4 empleados.
```

## Mantenimiento de perfiles

- **Reindexar:** si cambias el modelo de embeddings (Configuración → Modelos), los perfiles quedan marcados como desactualizados. Pulsa **Reindexar** para poder buscar en ellos otra vez.
- **Mostrar carpeta de documentos en Finder:** la app guarda una copia de cada documento en `~/Library/Application Support/NextHelp/Perfiles/<perfil>/`. Tus archivos originales **no se tocan**.
- **Borrar perfil:** elimina su índice y las copias; tus archivos originales siguen intactos.
- Si usas un proveedor en la nube con un perfil, las partes de tus documentos que se necesiten **salen de tu Mac** hacia ese servicio.

# 8. Resumen, guardado y memoria

## Título de la reunión

Escribe un nombre en el campo **Título de la reunión** y confirma con **Intro**. El archivo del guardado automático se renombra, no se crea otro. Si no escribes nada, después de un rato de conversación la app propone un título corto con el modelo rápido; si escribes uno tú, ya no lo cambia.

## Resumen de la reunión

Pulsa **Resumen** para obtener un resumen corto con **decisiones y pendientes** hasta ese momento. Aparece como una tarjeta en Respuestas. Cada vez que lo pulsas, el resumen se actualiza con lo nuevo, sin empezar de cero; si no hubo novedades, la app te lo dice. Usa **Copiar resumen** para llevarlo al portapapeles. Si hay muy poco dicho, avisa que todavía no hay qué resumir.

## Guardar como… y Abrir reciente

- **Guardado automático.** Cada reunión se guarda sola como `AAAA-MM-DD_HH-mm · Título.txt` (o `reunion-AAAA-MM-DD_HH-mm.txt` si no tiene título) junto a un `.json` con la reunión completa, que sirve para restaurarla.
- **Guardar como…** exporta la transcripción como `.txt`, `.md` o `.json` en el lugar que elijas.
- **Abrir reciente** muestra tus transcripciones guardadas. Se abren en **solo lectura**; si tienen `.json`, el botón **Restaurar** las carga en la ventana principal (la reunión actual se guarda antes).

## Memoria entre reuniones

NextHelp resume la reunión **en segundo plano** y guarda **hechos breves** (decisiones, pendientes, personas, cifras). Con eso responde con más contexto sin releer toda la transcripción y puede recordar reuniones anteriores. Solo se guardan resúmenes y hechos, **nunca la transcripción literal**. Los resúmenes automáticos pueden contener errores.

En **Configuración → Memoria** puedes:

- Activar o desactivar **Recordar entre reuniones** (viene activado). Desactivada, la memoria solo vive durante la reunión en curso y no se guarda nada.
- Ver los **hechos guardados** y los **resúmenes guardados**, y **borrar** cada uno.
- **Exportar…** la memoria a un archivo `.json`.
- **Borrar toda la memoria** (no se puede deshacer; las transcripciones guardadas no se tocan).

Si usas un proveedor en la nube, el resumen y los hechos relevantes viajan a ese proveedor como parte de la pregunta (solo si aceptaste su aviso de privacidad). La memoria se guarda en `~/Library/Application Support/NextHelp/memory.sqlite`.

# 9. Teleprompter

El teleprompter te ayuda a presentar una demo o una exposición sin perder el hilo.

![Teleprompter en la tercera columna (ilustración)](img/fig2.png)

1. Pulsa **Teleprompter** (botón 6) para mostrarlo. **Para quitarlo, vuelve a pulsar el mismo botón.**
2. En la columna del teleprompter, pulsa el botón de documento (**A**) para **abrir un guion** `.md` o `.txt`, o el de carpeta para abrir la carpeta de guiones (`~/Documents/MeetingAssistant/Guiones/`).
3. La tarjeta (**B**) muestra el **paso actual** y, abajo, el siguiente. El contador (**D**) indica «Paso 1 de 6» y las flechas cambian de paso.
4. Elige el **modo** (**C**):

| Modo | Cómo avanza |
|---|---|
| **Voz** | Te sigue mientras lees en voz alta: avanza cuando dices el **inicio** y el **final** del paso. |
| **Velocidad** | Se desplaza solo, a las palabras por minuto que elijas. |
| **Manual** | Tú lo mueves con las flechas o tocando un paso. |

## Formato del guion

Un archivo de texto o Markdown con estas reglas:

- Una **línea normal** es lo que **dices**. Con ella se detecta tu avance en modo Voz.
- Una línea entre **dobles asteriscos** (`**así**`) es lo que **haces en pantalla** (una acción).
- Una **línea en blanco** separa un paso del siguiente.
- Una línea que empieza con `#` es un **título** de sección (opcional).

```markdown
# Demo de producto

Buenas tardes a todos, hoy les voy a mostrar cómo funciona el módulo de reportes.
**Comparte pantalla con el panel abierto**

Aquí vemos el resumen de ventas del mes, por región.
**Señala la gráfica de barras**
```

# 10. Compartir pantalla y ventana

- **Visible / Invisible al compartir (7).** Cuando está en «Invisible», la ventana de NextHelp no aparece en lo que ven los demás al compartir pantalla, pero tú sí la ves. **Pruébalo siempre con una llamada de práctica antes de una reunión importante**, porque cada app de videollamada captura la pantalla a su manera.
- **Encima de todo (8).** Mantiene la ventana visible sobre las demás apps.
- **Apariencia (9).** Ajusta la transparencia del fondo y del texto, el color del texto (Auto, Blanco o Negro) y el **modo compacto**, que deja solo íconos para una ventana mucho más baja y angosta. Para ahorrar energía, el ajuste automático del color según el fondo se pausa cuando la ventana no se ve.
- **Zoom (13).** Hace más grande o más chica toda la app (⌘+ y ⌘−).

# 11. Voz e idiomas

Está en **Configuración → Voz**. Todo se reconoce en tu Mac, sin internet.

- **Idioma de la voz:** *Español + inglés* (recomendado: usa dos reconocedores y elige, palabra por palabra, el más seguro; sirve para frases en español con términos en inglés), *Solo español* o *Solo inglés*.
- **Cambio de idioma:** *Conservador* (favorece el idioma que domina la frase), *Normal* o *Sensible* (detecta cualquier palabra en otro idioma).
- **Vocabulario propio:** nombres, siglas y términos que salen mal; uno por línea o separados por comas. Al aplicarlo, la transcripción se reinicia unos segundos.
- **Idioma de la app:** en **Configuración → General** (español, inglés, chino simplificado, hindi y francés). No cambia el idioma en que se transcribe ni al que se traduce.

Si macOS no tiene el dictado sin conexión del idioma, actívalo en **Ajustes del Sistema → Teclado → Dictado**.

# 12. Modelos, contexto, proveedores y rendimiento

Todo esto se cambia en **Configuración**, y la configuración inicial (**Balanceado**) funciona bien en casi cualquier Mac.

## Modelos

Elige qué modelo usa cada función: respuestas rápidas, razonamiento y **embeddings** (la búsqueda en documentos; es obligatorio para usar perfiles con documentos). Puedes **instalar modelos** de la biblioteca de Ollama; la app marca los recomendados para tu Mac. Cambiar el modelo de embeddings requiere reindexar los perfiles.

## Contexto

Es cuánto puede leer la IA a la vez (transcripción, documentos y pregunta). Más contexto lee más reunión, pero usa más memoria:

| Opción | Lee aproximadamente | Recomendación |
|---|---|---|
| Ligero | 4 min de reunión | Muy rápido, poca memoria. |
| **Balanceado** (predeterminado) | 8 min | Equilibrio para casi cualquier Mac. |
| Amplio | 16 min | Usa más memoria. |
| Muy amplio | 30 min | Desde 16 GB de RAM. |
| Máximo | 1 hora | Solo con 32 GB de RAM o más. |

Con la memoria de la reunión (sección 8), lo más antiguo no se pierde: queda en el resumen y en los hechos guardados, y la IA recibe además lo último que se dijo. Si la reunión no cabe, se recorta lo más antiguo y la app te avisa junto a la respuesta.

**Razonar usa la misma ventana que Rápido**. Así, cambiar entre un modo y otro no obliga a Ollama a recargar el modelo y se evitan esperas de varios segundos. El razonamiento comparte ese espacio con la respuesta.

## Rendimiento y memoria de tu Mac

NextHelp ajusta cuánto tiempo deja los modelos cargados según la RAM que tiene tu Mac, para que no la sature mientras usas otras apps:

| Tu Mac | Modelos cargados a la vez | Tiempo cargados sin uso | Resumen automático |
|---|---|---|---|
| 8 GB o menos | 1 | 5 min | Cada ~3,000 tokens nuevos o ~10 min |
| 9 a 15 GB | 2 | 15 min | Cada ~2,000 tokens nuevos o ~7 min |
| 16 GB o más | Los que Ollama decida (hasta 3) | 30 min | Cada ~1,500 tokens nuevos o ~5 min |

Además:

- La app **precarga** el modelo rápido al iniciar para que la primera respuesta salga antes. En Macs de 8 GB no precarga el modelo de embeddings, para no sacar de memoria al modelo rápido.
- Si ves **«Cargando el modelo en memoria… la primera respuesta tarda más»**, el modelo se está cargando; las siguientes respuestas serán más rápidas.
- El resumen automático **se pospone** si hay una pregunta en curso, y también si macOS reporta poca memoria o la Mac está muy caliente. Una pregunta tuya siempre tiene prioridad.
- La atención flash (flash attention) está siempre activada para usar menos memoria. En **Servicios** puedes ahorrar aún más con el **KV cache comprimido**.
- Si el razonamiento se alarga demasiado sin dar texto, la app corta y redacta la respuesta con lo que alcanzó a pensar.

## Proveedores

Un proveedor es el servicio que ejecuta los modelos. **Ollama** (local) es el predeterminado y nada sale de tu Mac. También puedes agregar uno **compatible con OpenAI** (OpenAI, OpenRouter, Groq, LM Studio y otros) o **Anthropic**, con tu propia API key. La clave se guarda en el **Llavero** de macOS.

Con un proveedor en la nube, lo que preguntes y las partes necesarias de la transcripción y de tus documentos **salen de tu Mac** hacia ese servicio. Por eso:

- **Aviso de envío de datos.** Un proveedor remoto queda desactivado hasta que aceptas, una vez, el aviso de qué datos saldrán de tu Mac. Si cambias su dirección, el aviso se vuelve a pedir. Puedes revisarlo con **Revisar aviso…**.
- **Direcciones seguras.** Las direcciones deben usar `https`. Se permite `http` solo hacia tu propio equipo o hacia un equipo de tu **red local**, y en ese caso la app te pide **confirmar** que confías en esa red, porque la clave y tus conversaciones viajarían sin cifrar. La clave nunca se envía por `http` a un servidor de Internet.

## Servicios

Muestra el estado de Ollama (dirección, puerto, versión), permite reiniciarlo y ver su registro, ahorrar memoria con el KV cache comprimido y **Copiar diagnóstico** para pedir soporte. NextHelp solo usa un Ollama con **firma oficial**: si encuentra otro programa en el puerto de siempre, no lo usa y arranca uno propio; si el Ollama instalado no es el oficial, te pide instalar la versión oficial desde aquí.

# 13. Atajos de teclado

| Atajo | Acción |
|---|---|
| **⌘↩** | Responder lo último. |
| **⌘ +** / **⌘ −** | Ampliar / reducir toda la app. |
| **Enter** / **Esc** | Guardar / cancelar la corrección de una línea. |

# 14. Casos de uso

- **Entrevista (para practicar).** Crea el perfil `mi_cv` con tu CV y tus proyectos en `.md` o `.docx`. Simula la entrevista con un amigo, y cuando te pregunten por un proyecto, pulsa **Responder lo último**: te propone una respuesta basada en tu propio CV. Úsala solo donde esté permitido.
- **Reunión en otro idioma.** Activa **Traducir**, elige el idioma y lee la traducción debajo de cada línea.
- **Clase en línea.** Crea un perfil por materia con tus apuntes y pregunta para repasar lo que el profesor acaba de decir. Al terminar, pulsa **Resumen** y **Guardar como…**.
- **Se te fue el hilo.** Pulsa **Resumen** o usa la pregunta libre («¿qué se acordó hasta ahora?») para ponerte al día en segundos.
- **Reuniones recurrentes.** Con la memoria activada, pregunta «¿qué quedó pendiente de la reunión pasada?» y NextHelp recuerda decisiones y pendientes anteriores.
- **Presentación o demo.** Escribe tu guion, ábrelo en el teleprompter en modo **Voz** y deja el botón en **Invisible al compartir**.

# 15. Solución de problemas

| Problema | Qué hacer |
|---|---|
| macOS solo ofrece «Mover a la papelera» o «Cerrar» y la app no abre. | Ejecuta en Terminal `xattr -dr com.apple.quarantine /Applications/NextHelp.app` y ábrela de nuevo. Es necesario una sola vez por cada versión instalada. |
| Dice que la app «está dañada». | Repite el comando anterior y comprueba que NextHelp esté en Aplicaciones, no dentro del DMG. |
| No transcribe lo que dicen los demás. | Revisa el permiso de **Grabación de pantalla y audio del sistema** y que **Silenciar audio interno** (14) no esté activo. |
| Tras actualizar, el audio de «Ellos» no funciona o se traba. | macOS liga los permisos a la firma de la app y puede estar usando los de otra versión. Ve a **Configuración → General → Resolver conflicto de permisos** y pulsa **Resolver y reiniciar**: quita del registro de macOS las copias antiguas, borra los permisos guardados y reabre la app. macOS te los pedirá otra vez: acéptalos. No se tocan tus perfiles, documentos ni transcripciones. |
| Veo «Audio del sistema interrumpido, reconectando…». | Es normal si cambiaste de pantalla o la Mac salió de reposo. La app reintenta sola; si dice «No se pudo reconectar», usa **Silenciar audio interno** y vuelve a activarlo. |
| No transcribe lo que digo yo. | Revisa el permiso de **Micrófono** y que **Mutear mi mic** (15) no esté activo. |
| No se traduce. | Revisa Ajustes del Sistema → General → Idioma y región → Idiomas de traducción, y descarga el idioma desde la lista de idiomas (11). |
| Solo se traduce lo que dicen los demás. | Es lo normal. Activa el botón **Mis frases**. |
| «El perfil … no tiene documentos indexados todavía». | Agrega documentos en Configuración → Perfiles, o cambia al perfil **general**. |
| Los documentos de un perfil no responden bien. | Revisa **Avisos sobre tus documentos**, reindexa el perfil y usa archivos con texto real y encabezados claros. |
| Un documento no se indexa. | El mensaje dice el motivo: formato no admitido, más de 20 MB, PDF con contraseña o sin texto (escaneo). Divídelo, quítale la contraseña o conviértelo a un PDF con texto o a `.md`. |
| Las respuestas tardan mucho. | Usa el modo **Rápido**, baja la ventana de contexto o elige un modelo más pequeño. La primera respuesta tras un rato sin usar la app puede tardar por la carga del modelo. |
| «Falta aceptar el aviso de privacidad de …». | Ve a Configuración → Proveedores, pulsa **Revisar aviso…** y acéptalo, o vuelve a un proveedor local. |
| «Conexión sin cifrar en tu red local». | Es un proveedor con `http` hacia un equipo de tu red. Confírmalo solo si confías en esa red, o cambia a `https`. |
| Ollama no responde. | Configuración → Servicios → **Reiniciar** y revisa el registro. |
| «Se encontró un Ollama … pero su firma no es la oficial». | NextHelp no ejecuta Ollamas sin firma oficial. Instala la versión oficial desde Configuración → Servicios. |
| Quiero mandar un reporte. | En **Configuración → General** usa **Reportar en GitHub** o **Escribir a soporte**: abren un mensaje ya preparado que tú revisas y envías. |

# 16. Dónde se guardan tus cosas

| Qué | Dónde |
|---|---|
| Transcripciones (`.txt` y `.json`) | `~/Documents/MeetingAssistant/Transcripciones/` |
| Guiones del teleprompter | `~/Documents/MeetingAssistant/Guiones/` |
| Perfiles y copias de documentos | `~/Library/Application Support/NextHelp/Perfiles/` |
| Índice de búsqueda de documentos | `~/Library/Application Support/NextHelp/index.sqlite` |
| Memoria entre reuniones | `~/Library/Application Support/NextHelp/memory.sqlite` |
| Modelos de Ollama | `~/.ollama` |

La carpeta de datos de la app es privada para tu usuario. **Desinstalar:** arrastra NextHelp a la papelera. Para borrar también sus datos, elimina las carpetas de la tabla.

# 17. Privacidad y uso responsable

- Por defecto, la transcripción y la IA corren en tu Mac. Zeedatik no recibe tus conversaciones ni tus documentos.
- Si conectas un proveedor de IA en la nube, el texto que envíes lo procesa ese proveedor bajo sus propios términos. NextHelp te muestra un aviso antes de activarlo y un indicador permanente mientras esté activo.
- La memoria guarda resúmenes y hechos, no la transcripción literal, y puedes borrarla cuando quieras.
- **Avisa y obtén el consentimiento** de las personas a las que transcribas, según la ley y las reglas de tu escuela o empresa.
- Respeta las reglas de la entrevista, el examen o la reunión en que lo uses.

Los textos completos están en [`legal/`](https://github.com/zeedatik/NextHelp/tree/main/legal) y en el **Aviso de privacidad** que aparece al abrir la app.

# 18. Soporte

¿Algo no funciona o tienes una idea? Abre un [Issue](https://github.com/zeedatik/NextHelp/issues) o escribe a soporte@zeedatik.com e indica tu versión de macOS y de NextHelp (Configuración → General). Para un diagnóstico, usa **Configuración → Servicios → Copiar diagnóstico**.

---

© 2026 [Zeedatik](https://zeedatik.com). Todos los derechos reservados.

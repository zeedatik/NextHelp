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

# 3. Primer arranque

**Términos y privacidad.** La primera vez debes leer y aceptar los Términos de uso y el Aviso de privacidad. Al aceptar, te haces responsable de avisar y obtener el consentimiento de las personas a las que transcribas.

**Permisos de macOS.** La app te pedirá:

| Permiso | Para qué sirve |
|---|---|
| Micrófono | Transcribir lo que dices tú. |
| Reconocimiento de voz | Convertir el audio en texto. |
| Grabación de pantalla y audio del sistema | Oír a los demás en la llamada («Ellos»). |

Si olvidas uno, actívalo en **Ajustes del Sistema → Privacidad y seguridad** y vuelve a abrir la app.

**Asistente de bienvenida.** Revisa tu Mac (memoria y disco libre), recomienda modelos y, si lo aceptas, **instala Ollama** (el programa que ejecuta los modelos locales) y **descarga los modelos recomendados**. No necesitas usar la terminal. Puede tardar varios minutos según tu conexión: espera a que termine antes de tu primera reunión. Si prefieres usar un servicio en la nube, elige **«Prefiero usar un proveedor en la nube»** y agrega tu proveedor (ver sección 11).

Al terminar verás **«Todo listo»**. Más adelante puedes repetir el asistente desde **Configuración → Servicios → Repetir bienvenida**.

# 4. Recorrido por la ventana

![Ventana principal de NextHelp (ilustración con contenido de ejemplo)](img/fig1.png)

La ventana tiene tres zonas: **A) Transcripción** (lo que se dice), **B) Respuestas** (lo que te sugiere la IA) y **C) el campo de aclaración con el botón «Responder lo último»**. Arriba está la barra de botones. Un botón en **azul** significa que esa función está activada.

| N.º | Botón | Qué hace |
|---|---|---|
| 1 | **Perfil** | Elige el grupo de documentos con el que se responde (sección 7). |
| 2 | **Rápido / Razonar** | Rápido responde en pocos segundos. Razonar hace que el modelo piense antes de responder: más preciso, pero puede tardar minutos. |
| 3 | **Configuración** | Modelos, ventana de contexto, voz, proveedores, servicios y perfiles. |
| 4 | **Nueva reunión** | Guarda la transcripción actual y empieza un archivo `.txt` nuevo. |
| 5 | **Transcripciones** | Abre la carpeta donde se guardan los `.txt` de cada reunión. |
| 6 | **Teleprompter** | Muestra u oculta el teleprompter (sección 8). Se quita con este mismo botón. |
| 7 | **Visible / Invisible al compartir** | Si está en «Invisible», esta ventana no se ve cuando compartes pantalla (sección 9). |
| 8 | **Encima de todo** | La ventana flota sobre las demás apps, también en pantalla completa y en todos los escritorios. |
| 9 | **Apariencia** | Transparencia del fondo y del texto, color del texto y modo compacto. |
| 10 | **Traducir** | Traduce en vivo y pone la traducción debajo de cada línea (sección 6). |
| 11 | **Idioma** | Lista de idiomas a los que se traduce («Traducir a»). |
| 12 | **Mis frases** | Traduce también lo que dices tú. Por defecto solo se traduce lo que dicen «Ellos». |
| 13 | **− 80 % +** | Reduce o amplía toda la app: texto, botones y ventana (⌘− y ⌘+). |
| 14 | **Silenciar audio interno** | Deja de transcribir lo que suena en la Mac («Ellos»). |
| 15 | **Mutear mi mic** | Deja de transcribir lo que dices tú. |

Los botones pueden mostrarse solo con su ícono (modo compacto). Pasa el cursor sobre uno para ver su descripción.

# 5. Transcripción y respuestas

## La transcripción

- Las líneas de **«Ellos»** vienen del audio de tu Mac. Las de **«Tú»**, de tu micrófono.
- Una línea en **cursiva** todavía no está confirmada: espera a que deje de estar en cursiva antes de corregirla.
- Para **corregir** una línea, pulsa su lápiz, edita el texto y confirma con **Enter** (o **Esc** para cancelar). Queda marcada como «Corregido a mano».
- Haz clic en una o varias líneas para **seleccionarlas**. Con **Borrar** las quitas de la transcripción y con **Limpiar** quitas la selección.
- Cada reunión se guarda sola en `~/Documents/MeetingAssistant/Transcripciones/reunion-AAAA-MM-DD_HH-mm.txt`. El archivo refleja también tus correcciones y borrados. **Nueva reunión** cierra el archivo actual y empieza otro.

## Pedir una respuesta

| Quiero... | Haz esto |
|---|---|
| Responder la última pregunta de «Ellos» | Pulsa **Responder lo último** o usa **⌘↩**. |
| Responder una parte específica | Selecciona una o varias líneas y pulsa **Responder selección**. |
| Darle contexto a la IA | Escribe una **aclaración opcional** (por ejemplo «se refiere al módulo Change Management»). Sirve para buscar mejor en tus documentos. |
| Hacer una pregunta libre | Escribe abajo en «Pregúntale algo sobre la reunión…». La IA lee toda la transcripción y los documentos del perfil. |
| Profundizar en una respuesta | Pulsa **Detallar**: agrega al mismo hilo una versión más desarrollada. |
| Preguntar sobre un hilo concreto | Pulsa **Seleccionado / Preguntar** en ese hilo; lo que escribas abajo se preguntará sobre él. |
| Detener una respuesta | Pulsa **Detener**. |

Cada respuesta indica de qué **fuentes** (documentos) salió. En modo **Razonar** puedes abrir **Ver razonamiento**.

# 6. Traducción

La traducción **se hace en tu Mac con el traductor de macOS, sin internet**.

1. Pulsa el botón **Traducir** (10). Se pone en azul y la traducción aparece debajo de cada línea.
2. Para elegir el idioma, abre la lista de idiomas junto al botón (11). Si a un idioma le falta el paquete (⬇︎), macOS te pide permiso para descargarlo **una sola vez**. Un ✓ indica que ya está listo, y «(vía modelo)» que se traducirá con el modelo de IA.
3. Para apagarla, vuelve a pulsar **Traducir**.

**Importante: por defecto solo se traduce lo que dicen «Ellos».** Si quieres ver también la traducción de lo que dices tú, pulsa el botón **Mis frases** (12), junto a la lista de idiomas. Se pone en azul cuando está activo; pulsa otra vez para apagarlo.

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
4. Espera a que termine la indexación (la app muestra el avance). Verás cuántos fragmentos tiene cada documento.
5. Cierra Configuración, elige el perfil en el selector y empieza a preguntar.

## Documentos admitidos

| Formato | Notas |
|---|---|
| **`.md` (Markdown)** | **El mejor formato.** Texto limpio, con títulos y secciones. |
| **`.txt`** | Texto plano. |
| **`.pdf`** | Debe tener **texto seleccionable**. Un PDF escaneado (solo imágenes) no se puede leer. |
| `.csv`, `.json` | Se leen como texto. |

Word (`.docx`), Excel (`.xlsx`) y PowerPoint (`.pptx`) **no se admiten todavía**. Si tu información está ahí, expórtala a PDF o cópiala a un `.md`.

## Cómo escribir buenos documentos

La app divide cada documento en fragmentos por **párrafos** (separados por una línea en blanco) de alrededor de 1,200 caracteres, y para cada pregunta busca los fragmentos más parecidos. Por eso conviene:

- **Un tema por sección**, con un título claro (`## Proyecto de tesis`).
- **Párrafos cortos separados por una línea en blanco.**
- Incluir **nombres, cifras y términos tal como los dirías** en una reunión.
- Un archivo por tema grande (un CV, una materia, un cliente) en lugar de un solo archivo enorme.

Ejemplo de un `.md` para entrevistas:

```markdown
# Ana Pérez — CV

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

# 8. Teleprompter

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

# 9. Compartir pantalla y ventana

- **Visible / Invisible al compartir (7).** Cuando está en «Invisible», la ventana de NextHelp no aparece en lo que ven los demás al compartir pantalla, pero tú sí la ves. **Pruébalo siempre con una llamada de práctica antes de una reunión importante**, porque cada app de videollamada captura la pantalla a su manera.
- **Encima de todo (8).** Mantiene la ventana visible sobre las demás apps.
- **Apariencia (9).** Ajusta la transparencia del fondo y del texto, el color del texto (Auto, Blanco o Negro) y el **modo compacto**, que deja solo íconos para una ventana mucho más baja y angosta.
- **Zoom (13).** Hace más grande o más chica toda la app (⌘+ y ⌘−).

# 10. Voz e idiomas

Está en **Configuración → Voz**. Todo se reconoce en tu Mac, sin internet.

- **Idioma de la voz:** *Español + inglés* (recomendado: usa dos reconocedores y elige, palabra por palabra, el más seguro; sirve para frases en español con términos en inglés), *Solo español* o *Solo inglés*.
- **Cambio de idioma:** *Conservador* (favorece el idioma que domina la frase), *Normal* o *Sensible* (detecta cualquier palabra en otro idioma).
- **Vocabulario propio:** nombres, siglas y términos que salen mal; uno por línea o separados por comas. Al aplicarlo, la transcripción se reinicia unos segundos.
- **Idioma de la app:** en **Configuración → General**. No cambia el idioma en que se transcribe ni al que se traduce.

Si macOS no tiene el dictado sin conexión del idioma, actívalo en **Ajustes del Sistema → Teclado → Dictado**.

# 11. Modelos, contexto y proveedores

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

Si la reunión no cabe, se recorta lo más antiguo y la app te avisa junto a la respuesta.

## Proveedores

Un proveedor es el servicio que ejecuta los modelos. **Ollama** (local) es el predeterminado y nada sale de tu Mac. También puedes agregar uno **compatible con OpenAI** (OpenAI, OpenRouter, Groq, LM Studio y otros) o **Anthropic**, con tu propia API key. La clave se guarda en el **Llavero** de macOS.

Con un proveedor en la nube, lo que preguntes y las partes necesarias de la transcripción y de tus documentos **salen de tu Mac** hacia ese servicio.

## Servicios

Muestra el estado de Ollama (dirección, puerto, versión), permite reiniciarlo y ver su registro, ahorrar memoria con el KV cache comprimido y **Copiar diagnóstico** para pedir soporte.

# 12. Atajos de teclado

| Atajo | Acción |
|---|---|
| **⌘↩** | Responder lo último. |
| **⌘ +** / **⌘ −** | Ampliar / reducir toda la app. |
| **Enter** / **Esc** | Guardar / cancelar la corrección de una línea. |

# 13. Casos de uso

- **Entrevista (para practicar).** Crea el perfil `mi_cv` con tu CV y tus proyectos en `.md`. Simula la entrevista con un amigo, y cuando te pregunten por un proyecto, pulsa **Responder lo último**: te propone una respuesta basada en tu propio CV. Úsala solo donde esté permitido.
- **Reunión en otro idioma.** Activa **Traducir**, elige el idioma y lee la traducción debajo de cada línea.
- **Clase en línea.** Crea un perfil por materia con tus apuntes en `.md` y pregunta para repasar lo que el profesor acaba de decir.
- **Se te fue el hilo.** Usa la pregunta libre («¿qué se acordó hasta ahora?») para recibir un resumen de lo último que se habló.
- **Presentación o demo.** Escribe tu guion, ábrelo en el teleprompter en modo **Voz** y deja el botón en **Invisible al compartir**.

# 14. Solución de problemas

| Problema | Qué hacer |
|---|---|
| macOS solo ofrece «Mover a la papelera» o «Cerrar» y la app no abre. | Ejecuta en Terminal `xattr -dr com.apple.quarantine /Applications/NextHelp.app` y ábrela de nuevo. Es necesario una sola vez. |
| Dice que la app «está dañada». | Repite el comando anterior y comprueba que NextHelp esté en Aplicaciones, no dentro del DMG. |
| No transcribe lo que dicen los demás. | Revisa el permiso de **Grabación de pantalla y audio del sistema** y que **Silenciar audio interno** (14) no esté activo. |
| macOS no reconoce el permiso de audio del sistema. | Cierra la app (⌘Q), quítala de Privacidad y seguridad → Grabación de pantalla y audio del sistema con el botón **−**, ejecuta `tccutil reset ScreenCapture com.luisrangel.meetingassistant`, reinicia la Mac y concede el permiso otra vez. |
| No transcribe lo que digo yo. | Revisa el permiso de **Micrófono** y que **Mutear mi mic** (15) no esté activo. |
| No se traduce. | Revisa Ajustes del Sistema → General → Idioma y región → Idiomas de traducción, y descarga el idioma desde la lista de idiomas (11). |
| Solo se traduce lo que dicen los demás. | Es lo normal. Activa el botón **Mis frases**. |
| «El perfil … no tiene documentos indexados todavía». | Agrega documentos en Configuración → Perfiles, o cambia al perfil **general**. |
| Los documentos de un perfil no responden bien. | Reindexa el perfil, usa archivos con texto real y secciones claras (`.md`). |
| Las respuestas tardan mucho. | Usa el modo **Rápido**, baja la ventana de contexto o elige un modelo más pequeño. |
| Ollama no responde. | Configuración → Servicios → **Reiniciar** y revisa el registro. |
| El PDF no se indexa. | Probablemente es un escaneo sin texto. Conviértelo con OCR o cópialo a un `.md`. |
| Tras actualizar, macOS vuelve a pedir permisos. | Es normal en cada versión nueva. Concédelos de nuevo. |

# 15. Dónde se guardan tus cosas

| Qué | Dónde |
|---|---|
| Transcripciones | `~/Documents/MeetingAssistant/Transcripciones/` |
| Guiones del teleprompter | `~/Documents/MeetingAssistant/Guiones/` |
| Perfiles y copias de documentos | `~/Library/Application Support/NextHelp/Perfiles/` |
| Modelos de Ollama | `~/.ollama` |

**Desinstalar:** arrastra NextHelp a la papelera. Para borrar también sus datos, elimina las carpetas de la tabla.

# 16. Privacidad y uso responsable

- Por defecto, la transcripción y la IA corren en tu Mac. Zeedatik no recibe tus conversaciones ni tus documentos.
- Si conectas un proveedor de IA en la nube, el texto que envíes lo procesa ese proveedor bajo sus propios términos.
- **Avisa y obtén el consentimiento** de las personas a las que transcribas, según la ley y las reglas de tu escuela o empresa.
- Respeta las reglas de la entrevista, el examen o la reunión en que lo uses.

Los textos completos están en [`legal/`](https://github.com/zeedatik/NextHelp/tree/main/legal) y en el **Aviso de privacidad** que aparece al abrir la app.

# 17. Soporte

¿Algo no funciona o tienes una idea? Abre un [Issue](https://github.com/zeedatik/NextHelp/issues) e indica tu versión de macOS y de NextHelp (Configuración → Servicios). Para un diagnóstico, usa **Configuración → Servicios → Copiar diagnóstico**.

---

© 2026 [Zeedatik](https://zeedatik.com). Todos los derechos reservados.

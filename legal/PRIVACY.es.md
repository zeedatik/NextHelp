# NextHelp — Aviso de privacidad

Versión 1.1 · Última actualización: 12 de octubre de 2026

Responsable: el equipo de NextHelp ("nosotros"). Contacto: https://github.com/zeedatik/NextHelp/issues

## 1. La versión corta

NextHelp no recopila tus datos. No tiene cuentas, ni analíticas, ni publicidad, ni reportes de fallos, ni telemetría. No operamos ningún servidor que reciba algo de la app. Todo lo que la app crea se queda en tu Mac, salvo que decidas conectar un proveedor de IA en la nube (sección 5).

## 2. Qué hace la app con tu audio

- **Micrófono ("Tú").** Con tu permiso, la app escucha tu micrófono y convierte la voz en texto en tu Mac con el reconocimiento de voz de Apple en el equipo (SpeechAnalyzer, o SFSpeechRecognizer en modo sin conexión en versiones anteriores de macOS). El audio no se graba en un archivo y no se nos envía.
- **Audio del sistema ("Ellos").** Con tu permiso de grabación de pantalla y audio del sistema, la app captura el audio que suena en tu Mac (por ejemplo, las demás personas de una videollamada) y lo transcribe igual. Solo se usa el audio; la app no guarda imágenes de la pantalla.
- Apple puede descargar a tu Mac paquetes de idioma de voz y traducción a través de macOS. Esas descargas las hace macOS bajo los términos de Apple.

## 3. Qué se guarda en tu Mac

| Qué | Dónde | Notas |
|---|---|---|
| Transcripciones (.txt) | ~/Documents/MeetingAssistant/Transcripciones/ | Se guardan solas durante la reunión. Pueden contener lo que dijeron otras personas. Bórralas cuando quieras. |
| Guiones del teleprompter | ~/Documents/MeetingAssistant/Guiones/ | Archivos que creas o importas. |
| Documentos de los perfiles y su índice de búsqueda | ~/Library/Application Support/NextHelp/ | Copias de los documentos que agregas a un perfil y un índice local para encontrar pasajes relevantes. |
| Ajustes | Preferencias de macOS (UserDefaults) | Ventana, idioma, modelos y opciones de apariencia. |
| Llaves de API | Llavero de macOS | Solo si agregas un proveedor en la nube. Nunca se escriben en archivos de texto. |
| Registro de diagnóstico | ~/Documents/MeetingAssistant/MeetingAssistant-debug.log | Apagado por defecto en la app publicada. Si lo activas para resolver un problema, puede incluir fragmentos de texto transcrito. Bórralo al terminar. |

Nosotros no podemos ver ni acceder a ninguno de estos archivos.

## 4. Cuándo salen datos de tu Mac

La app solo se conecta a la red para lo que tú inicias o eliges:

- **Ollama y modelos.** Si aún no tienes Ollama, el asistente de instalación lo descarga de la página oficial de versiones del proyecto Ollama en GitHub y comprueba su firma antes de ejecutarlo. Los modelos los descarga Ollama desde su biblioteca. Después, Ollama corre en tu Mac.
- **Un servidor de IA local o remoto que configures** (por ejemplo LM Studio u otra computadora de tu red). El texto va a la dirección que escribiste.
- **Un proveedor de IA en la nube que configures** (sección 5).
- **macOS.** Los servicios propios de Apple, como la descarga de paquetes de idioma, los gestiona macOS.

La app no contiene código que nos envíe datos de uso.

## 5. Proveedores de IA en la nube

Si agregas un proveedor como OpenAI, Anthropic, Groq u OpenRouter, la app envía a ese proveedor, con tu llave de API, el texto necesario para esa solicitud (por ejemplo, la parte de la transcripción sobre la que preguntas, tu pregunta y los fragmentos relevantes de los documentos de tu perfil). Ese proveedor lo recibe y lo procesa bajo su propia política de privacidad, y nosotros no controlamos lo que haga con ello. La app marca los proveedores que envían datos fuera de tu computadora. Si quieres que todo se quede en tu Mac, usa un modelo local con Ollama.

## 6. Datos de otras personas

Las transcripciones pueden contener información personal y voces de otras personas. Eres responsable de informarles y de obtener su consentimiento cuando la ley lo exija (consulta los Términos de uso), y de guardar y borrar las transcripciones de forma responsable.

## 7. Tus derechos

Como no conservamos tus datos personales, no hay nada que podamos consultar, rectificar o eliminar en tu nombre: tú controlas todos los datos directamente borrando los archivos indicados arriba o eliminando la app. Si crees que conservamos datos personales tuyos de otra manera, escríbenos al contacto de arriba y responderemos conforme a la ley aplicable, incluida la ley mexicana de protección de datos personales.

## 8. Menores

La app no está dirigida a menores de 13 años y no recopilamos a sabiendas información de ellos (no recopilamos información de nadie).

## 9. Cambios

Si este aviso cambia de forma importante, la app te pedirá revisar y aceptar la nueva versión. La versión vigente siempre se incluye con la app y en el repositorio del proyecto.

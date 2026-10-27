# Installing NextHelp / Instalar NextHelp

By default NextHelp runs on your Mac, and we never receive your conversations or documents. · Por defecto NextHelp corre en tu Mac y nosotros nunca recibimos tus conversaciones ni tus documentos.

## English

> After installing, see the [User Manual](manual-de-usuario/User-Manual.en.pdf) for how to use NextHelp.

**Requirements:** a Mac with Apple silicon, macOS 15 or later (macOS 26 recommended: best transcription and translation), about 5–10 GB of free disk if you want local AI models.

1. Download `NextHelp-x.y.dmg` from the [Releases page](https://github.com/zeedatik/NextHelp/releases). Optional: check that its SHA-256 matches the `.sha256` file (`shasum -a 256 NextHelp-x.y.dmg`).
2. Open the DMG and drag **NextHelp** into **Applications**.
3. **Remove the download flag (required, once).** NextHelp is not yet notarized by Apple, so the first time you open it macOS shows a message with only **Move to Trash** and **Done**, and the app will not start. Do not move it to the Trash. Click **Done**, open **Terminal** (Applications → Utilities → Terminal), paste this command and press Enter:

   ```bash
   xattr -dr com.apple.quarantine /Applications/NextHelp.app
   ```

   It prints nothing when it works. This only removes the "downloaded from the internet" mark from NextHelp. Do it only with the official DMG from this repository.
4. Open NextHelp from Applications. It now opens normally.
5. Read and accept the Terms of Use and Privacy Policy.
6. Allow the permissions macOS asks for: **Microphone**, **Speech Recognition** and **Screen & System Audio Recording** (to hear the other people in a call). If you miss one, enable it in System Settings → Privacy & Security and reopen the app.
7. Follow the setup assistant. It can install a local AI runtime (Ollama) and download the recommended models (this can take a while and needs free disk and an internet connection), or you can use your own cloud provider key. Wait for the models to finish downloading before your first meeting.

Tested on a new Mac with nothing previously installed: steps 1 to 7 are enough.

**Updating:** quit NextHelp (⌘Q), drag the new **NextHelp** into **Applications** replacing the old one, run the `xattr` command from step 3 again and open the app. Your profiles, documents and transcripts are kept. If the "Them" audio fails after updating, use **Settings → General → Resolve permissions conflict**.

**Uninstall:** drag NextHelp to the Trash. To remove its data also delete `~/Library/Application Support/NextHelp/`, `~/Documents/MeetingAssistant/` (transcripts and scripts) and, if you want, the models in `~/.ollama`.

## Español

> Después de instalar, consulta el [Manual de usuario](manual-de-usuario/Manual-de-usuario.es.pdf) para aprender a usar NextHelp.

**Requisitos:** una Mac con chip Apple, macOS 15 o superior (se recomienda macOS 26: mejor transcripción y traducción), y de 5 a 10 GB libres si quieres modelos de IA locales.

1. Descarga `NextHelp-x.y.dmg` de la [página de Releases](https://github.com/zeedatik/NextHelp/releases). Opcional: comprueba que su SHA-256 coincida con el archivo `.sha256` (`shasum -a 256 NextHelp-x.y.dmg`).
2. Abre el DMG y arrastra **NextHelp** a **Aplicaciones**.
3. **Quita la marca de descarga (obligatorio, una sola vez).** NextHelp todavía no está notarizada por Apple, así que la primera vez que la abres macOS muestra un aviso con solo **Mover a la papelera** y **Cerrar**, y la app no inicia. No la muevas a la papelera. Pulsa **Cerrar**, abre **Terminal** (Aplicaciones → Utilidades → Terminal), pega este comando y pulsa Enter:

   ```bash
   xattr -dr com.apple.quarantine /Applications/NextHelp.app
   ```

   Si funciona no imprime nada. Solo quita de NextHelp la marca de "descargado de internet". Hazlo únicamente con el DMG oficial de este repositorio.
4. Abre NextHelp desde Aplicaciones. Ahora abre con normalidad.
5. Lee y acepta los Términos de uso y el Aviso de privacidad.
6. Concede los permisos que pida macOS: **Micrófono**, **Reconocimiento de voz** y **Grabación de pantalla y audio del sistema** (para oír a los demás en una llamada). Si olvidas uno, actívalo en Ajustes del Sistema → Privacidad y seguridad y reabre la app.
7. Sigue el asistente de configuración. Puede instalar un motor de IA local (Ollama) y descargar los modelos recomendados (puede tardar y necesita espacio libre y conexión a internet), o puedes usar la llave de tu proveedor en la nube. Espera a que terminen de descargarse los modelos antes de tu primera reunión.

Probado en una Mac nueva sin nada instalado previamente: con los pasos 1 a 7 es suficiente.

**Actualizar:** cierra NextHelp (⌘Q), arrastra el nuevo **NextHelp** a **Aplicaciones** reemplazando el anterior, ejecuta otra vez el comando `xattr` del paso 3 y abre la app. Tus perfiles, documentos y transcripciones se conservan. Si el audio de «Ellos» falla después de actualizar, usa **Configuración → General → Resolver conflicto de permisos**.

**Desinstalar:** arrastra NextHelp a la papelera. Para borrar también sus datos elimina `~/Library/Application Support/NextHelp/`, `~/Documents/MeetingAssistant/` (transcripciones y guiones) y, si quieres, los modelos en `~/.ollama`.

## Solución de problemas / Troubleshooting

### Español

**El audio del sistema («Ellos») no funciona, se traba o macOS no reconoce el permiso.** Suele pasar después de instalar una versión nueva de la app, porque macOS liga los permisos a la firma de la versión anterior. Se arregla desde la propia app:

1. Abre **Configuración** (el ícono de engrane).
2. Entra a **General**.
3. En la sección **Permisos de audio**, pulsa **Resolver conflicto de permisos** y confirma con **Resolver y reiniciar**.
4. Espera a que la app se cierre sola y se vuelva a abrir.
5. Concede otra vez los permisos que macOS te pida (micrófono, reconocimiento de voz y grabación de pantalla y audio del sistema).

Listo: con eso queda resuelto. Este botón no toca tus perfiles, documentos ni transcripciones.

### English

**System audio ("Them") doesn't work, hangs, or macOS doesn't recognize the permission.** This usually happens after installing a new version of the app, because macOS ties permissions to the previous version's signature. You can fix it from inside the app:

1. Open **Settings** (the gear icon).
2. Go to **General**.
3. In the **Audio permissions** section, press **Resolve permissions conflict** and confirm with **Resolve and restart**.
4. Wait for the app to close and reopen by itself.
5. Grant again the permissions macOS asks for (microphone, speech recognition and screen & system audio recording).

That's it: everything works again. This button does not touch your profiles, documents or transcripts.

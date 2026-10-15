# Installing NextHelp / Instalar NextHelp

NextHelp runs on your Mac. Nothing is sent to us. · NextHelp corre en tu Mac. No se nos envía nada.

## English

**Requirements:** a Mac with Apple silicon, macOS 15 or later (macOS 26 recommended: best transcription and translation), about 5–10 GB of free disk if you want local AI models.

1. Download `NextHelp-x.y.dmg` from the [Releases page](https://github.com/zeedatik/NextHelp/releases). Optional: check that its SHA-256 matches the `.sha256` file (`shasum -a 256 NextHelp-x.y.dmg`).
2. Open the DMG and drag **NextHelp** into **Applications**.
3. Open NextHelp from Applications. macOS says it cannot verify the developer, because the app is not notarized by Apple. Click **Cancel** (not "Move to Trash").
4. Open **System Settings → Privacy & Security**, scroll to **Security** and click **Open Anyway** next to the NextHelp message. Confirm with your password or Touch ID. You only do this once.
5. Read and accept the Terms of Use and Privacy Policy.
6. Allow the permissions macOS asks for: **Microphone**, **Speech Recognition** and **Screen & System Audio Recording** (to hear the other people in a call). If you miss one, enable it in System Settings → Privacy & Security and reopen the app.
7. Follow the setup assistant. It can install a local AI runtime (Ollama) and download models, or you can use your own cloud provider key.

If macOS says the app **"is damaged and can't be opened"**, remove the download flag once (only for software you trust) in Terminal:

```bash
xattr -dr com.apple.quarantine /Applications/NextHelp.app
```

**Uninstall:** drag NextHelp to the Trash. To remove its data also delete `~/Library/Application Support/NextHelp/`, `~/Documents/MeetingAssistant/` (transcripts and scripts) and, if you want, the models in `~/.ollama`.

## Español

**Requisitos:** una Mac con chip Apple, macOS 15 o superior (se recomienda macOS 26: mejor transcripción y traducción), y de 5 a 10 GB libres si quieres modelos de IA locales.

1. Descarga `NextHelp-x.y.dmg` de la [página de Releases](https://github.com/zeedatik/NextHelp/releases). Opcional: comprueba que su SHA-256 coincida con el archivo `.sha256` (`shasum -a 256 NextHelp-x.y.dmg`).
2. Abre el DMG y arrastra **NextHelp** a **Aplicaciones**.
3. Abre NextHelp desde Aplicaciones. macOS dirá que no puede verificar al desarrollador, porque la app no está notarizada por Apple. Pulsa **Cancelar** (no "Mover a la papelera").
4. Abre **Ajustes del Sistema → Privacidad y seguridad**, baja a **Seguridad** y pulsa **Abrir de todos modos** junto al aviso de NextHelp. Confirma con tu contraseña o Touch ID. Solo se hace una vez.
5. Lee y acepta los Términos de uso y el Aviso de privacidad.
6. Concede los permisos que pida macOS: **Micrófono**, **Reconocimiento de voz** y **Grabación de pantalla y audio del sistema** (para oír a los demás en una llamada). Si olvidas uno, actívalo en Ajustes del Sistema → Privacidad y seguridad y reabre la app.
7. Sigue el asistente de configuración. Puede instalar un motor de IA local (Ollama) y descargar modelos, o puedes usar la llave de tu proveedor en la nube.

Si macOS dice que la app **"está dañada y no se puede abrir"**, quita la marca de descarga una vez (solo para software de confianza) en Terminal:

```bash
xattr -dr com.apple.quarantine /Applications/NextHelp.app
```

**Desinstalar:** arrastra NextHelp a la papelera. Para borrar también sus datos elimina `~/Library/Application Support/NextHelp/`, `~/Documents/MeetingAssistant/` (transcripciones y guiones) y, si quieres, los modelos en `~/.ollama`.

## Solución de problemas / Troubleshooting

**Español — El audio del sistema no funciona o macOS no reconoce el permiso.** Mantén **una sola copia** de NextHelp, en Aplicaciones, y ábrela desde ahí (no desde el DMG montado). Cierra la app (⌘Q), quita NextHelp de **Ajustes del Sistema → Privacidad y seguridad → Grabación de pantalla y audio del sistema** con el botón **−**, y ejecuta en Terminal:

```bash
tccutil reset ScreenCapture com.luisrangel.meetingassistant
```

Reinicia la Mac, abre NextHelp y vuelve a conceder el permiso cuando macOS lo pida. Después de actualizar a una versión nueva, macOS puede volver a pedir los permisos de micrófono y de audio del sistema.

**English — System audio doesn't work or macOS doesn't recognize the permission.** Keep **a single copy** of NextHelp in Applications and open it from there (not from the mounted DMG). Quit the app (⌘Q), remove NextHelp from **System Settings → Privacy & Security → Screen & System Audio Recording** with the **−** button, and run in Terminal:

```bash
tccutil reset ScreenCapture com.luisrangel.meetingassistant
```

Restart your Mac, open NextHelp and grant the permission again when macOS asks. After updating to a new version, macOS may ask for the microphone and system-audio permissions again.

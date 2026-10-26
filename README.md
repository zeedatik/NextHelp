<div align="center">

# NextHelp

**Tu copiloto para cualquier reunión.** · *Your copilot for any meeting.*

macOS (Apple Silicon) · Gratis · by [Zeedatik](https://zeedatik.com)

[**Descargar / Download**](https://github.com/zeedatik/NextHelp/releases/latest) · [Instalación / Install](INSTALL.md) · [Manual](manual-de-usuario/Manual-de-usuario.es.pdf) / [User Manual](manual-de-usuario/User-Manual.en.pdf) · [Soporte / Support](https://github.com/zeedatik/NextHelp/issues)

</div>





https://github.com/user-attachments/assets/1a9a7327-6061-45d5-aa72-8b84d3d237af





---

## Español

NextHelp es una app para Mac que te acompaña durante una reunión o una llamada: escucha, transcribe y te sugiere qué responder, con la información de tus propios documentos.

### Qué hace

- **Transcripción en vivo** de lo que se dice, de tu micrófono y del audio de la llamada.
- **Traducción al instante**, en el idioma que elijas.
- **Respuestas con tus documentos**: pregunta algo y responde a partir de tus archivos, citando de dónde salió. Puedes limitarlo a *solo tus documentos*.
- **Teleprompter que te sigue** mientras lees en voz alta.
- **Se oculta al compartir pantalla**, para que la ventana de NextHelp no aparezca en lo que ven los demás.
- **Un perfil para cada tema**, con sus propios documentos y ajustes.
- Interfaz en **5 idiomas**.

### Privacidad, en corto

- Por defecto, la transcripción y la IA **corren en tu Mac**, con modelos locales.
- Si tú decides conectar un proveedor de IA en la nube (con tu propia llave de API), el texto que envíes lo procesa ese proveedor bajo sus propios términos.
- Zeedatik no recibe tus conversaciones ni tus documentos.
- Detalles completos en el Aviso de privacidad que aparece al abrir la app por primera vez.

### Requisitos

- Mac con **chip Apple (M1 o posterior)**. No hay versión para Mac con Intel.
- **macOS 15 o posterior** (se recomienda macOS 26: mejor transcripción y traducción).
- De 5 a 10 GB libres si quieres modelos de IA locales.

### Instalar

1. Descarga el `.dmg` de la [página de Releases](https://github.com/zeedatik/NextHelp/releases/latest).
2. Ábrelo y arrastra **NextHelp** a **Aplicaciones**.
3. La app aún no está notarizada por Apple, así que macOS no la deja abrir la primera vez (solo ofrece "Mover a la papelera" o "Cerrar"). Pulsa **Cerrar**, abre **Terminal** y ejecuta una sola vez:

   ```bash
   xattr -dr com.apple.quarantine /Applications/NextHelp.app
   ```

4. Abre NextHelp desde Aplicaciones, concede los permisos que pida (micrófono, reconocimiento de voz y grabación de pantalla y audio del sistema) y deja que descargue los modelos de IA locales recomendados.

Pasos completos, permisos y solución de problemas en [INSTALL.md](INSTALL.md).

### Manual de usuario

Cómo usar cada botón, la traducción, los perfiles y documentos, el resumen y la memoria, el teleprompter y más: [Manual en PDF](manual-de-usuario/Manual-de-usuario.es.pdf) · [Manual en Markdown](manual-de-usuario/Manual-de-usuario.es.md).

### Soporte

¿Algo no funciona o tienes una idea? Abre un [Issue](https://github.com/zeedatik/NextHelp/issues). Indica tu versión de macOS y de NextHelp.

---

## English

NextHelp is a Mac app that keeps you company during a meeting or call: it listens, transcribes, and suggests what to say, using information from your own documents.

### What it does

- **Live transcription** of what is said, from your microphone and the call audio.
- **Instant translation** into the language you choose.
- **Answers from your documents**: ask something and get a reply based on your files, showing where it came from. You can restrict it to *your documents only*.
- **A teleprompter that follows you** while you read aloud.
- **Hides when you share your screen**, so the NextHelp window doesn't show up for others.
- **One profile per topic**, with its own documents and settings.
- Interface in **5 languages**.

### Privacy, briefly

- By default, transcription and AI **run on your Mac**, using local models.
- If you choose to connect a cloud AI provider (with your own API key), the text you send is processed by that provider under its own terms.
- Zeedatik does not receive your conversations or documents.
- Full details are in the Privacy Notice shown the first time you open the app.

### Requirements

- A Mac with **Apple silicon (M1 or later)**. There is no Intel version.
- **macOS 15 or later** (macOS 26 recommended: better transcription and translation).
- 5–10 GB of free disk if you want local AI models.

### Install

1. Download the `.dmg` from the [Releases page](https://github.com/zeedatik/NextHelp/releases/latest).
2. Open it and drag **NextHelp** into **Applications**.
3. The app is not yet notarized by Apple, so macOS will not open it the first time (it only offers "Move to Trash" or "Done"). Click **Done**, open **Terminal** and run this once:

   ```bash
   xattr -dr com.apple.quarantine /Applications/NextHelp.app
   ```

4. Open NextHelp from Applications, grant the permissions it asks for (microphone, speech recognition and screen & system audio recording) and let it download the recommended local AI models.

Full steps, permissions and troubleshooting in [INSTALL.md](INSTALL.md).

### User manual

How to use every button, translation, profiles and documents, summary and memory, the teleprompter and more: [Manual (PDF)](manual-de-usuario/User-Manual.en.pdf) · [Manual (Markdown)](manual-de-usuario/User-Manual.en.md).

### Support

Something not working, or have an idea? Open an [Issue](https://github.com/zeedatik/NextHelp/issues). Please include your macOS and NextHelp versions.

---

## Licencia · License

NextHelp es software **propietario y gratuito**: puedes instalarlo y usarlo según sus Términos de uso, pero el código fuente no es público y no está permitido redistribuir, modificar ni hacer ingeniería inversa del software. Ver [LICENSE](LICENSE). Los componentes de terceros que NextHelp puede usar están en [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).

NextHelp is **proprietary, free** software: you may install and use it under its Terms of Use, but the source code is not public and redistribution, modification and reverse engineering are not permitted. See [LICENSE](LICENSE).

© 2026 [Zeedatik](https://zeedatik.com). Todos los derechos reservados · All rights reserved.

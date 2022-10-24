## TD Twitch 💬

`ES`
Este es un componente de [TouchDesigner](https://derivative.ca/) para recibir y filtrar mensajes del chat de un stream de [Twitch](https://www.twitch.tv/).
El componente `TDTwitch.tox` filtra los mensajes en tiempo real gracias a [WebSockets](https://developer.mozilla.org/es/docs/Web/API/WebSockets_API). Además tiene la funcionalidad de controlar el output de video (captura de pantalla, webcam, etc) usando [NDI](https://www.ndi.tv/tools/) y [OBS Studio](https://obsproject.com/es/download). Ambas funcionalidades funcionan de manera independiente.
> 💡 Nota: debido a una incompatibilidad en OBS v28, para utilizar la funcionalidad de video es necesario instalar [OBS Studio v27.2.4](https://github.com/obsproject/obs-studio/releases/tag/27.2.4) o anterior.


### Recomendación 🚧
Es recomendable descargar previamente [OBS Studio](https://obsproject.com/es/download) y sinconcrizarlo a tu cuenta de Twitch previamente, así podes testear el componente desde el chat de OBS, sin la necesidad de stremear contenido o hacer pruebas en vivo.

```
# abrir OBS Studio
PANELES --> CHAT
```

### Rápida integración e implementación del filtro de mensajes 🚩 

Simplemente arrastrar el archivo `.tox` en el proyecto en el que estes trabajando.
Para conectarse a la infraestructura IRC de Twitch es necesario completar con la propia información en la pestaña `Settings`.

- `OAuth Token`: log-in en Twitch y luego generar el token en [https://twitchapps.com/tmi/].
	> 💡 Nota: es recomendable no compartir ni publicar el token para mantener la seguridad de la cuenta.
- `Nickname`: es el nombre de tu nombre de usuario en [Twitch](https://www.twitch.tv/).
- `Channel`: es el nombre del canal de [Twitch](https://www.twitch.tv/) al que te queres conectar.

Una vez configurado, deberías poder empezar a escuchar los mensajes entrantes.
> 💡 Nota: en el caso de que esto no suceda apagar y prender el componente o pulsar en restart.

`Network Address` y `Network Port`: deberían quedar igual por default y no deberían ser tocados, salvo que cambie algo en la infraestructura de Twitch.

`Keyword`: letra o palabra clave para elegir que mensajes se filtran. Por default es `!`. Si se quieren filtrar todos los mensajes, es necesario dejarlo vacío.

El resto de los parámetros modificarlos a gusto.

### Rápida integración e implementación con NDI y OBS 🎛

En el caso de que se quiera tener control también de la parte visual del stream, es posible manejar esto desde TouchDesigner.

1. Instalar [OBS Studio v27.2.4](https://github.com/obsproject/obs-studio/releases/tag/27.2.4).
	> 💡 Ej.: en Windows --> `OBS-Studio-27.2.4-Full-Installer-x64.exe`

2. Instalar [NDI Tools](https://www.ndi.tv/tools/).

3. Instalar [obs-ndi v4.9.1](https://github.com/Palakis/obs-ndi/releases/tag/4.9.1)
	> 💡 Ej.: en Windows --> `obs-ndi-4.9.0-Windows-Installer.exe`

4. Abrir la aplicación NDI y seleccionar NDI Screen Capture.

5. Configurar con tus dispositivos de entrada.

Para conectarse a OBS Studio via NDI es necesario ir a la pestaña `Video` en el componente `TDTwitch`.
**In** `Active`: ON.
`Source Name`: Elegir tu dispositivo de entrada configurado (captura de pantalla, webcam, etc).

**Out** `Active`: ON.

Una vez configurado, deberías ver input de video.
> 💡 Nota: en el caso de que esto no suceda, revisar la configuración de NDI.

El resto de los parámetros modificarlos a gusto.

Luego, en OBS Studio:

```
Agregar --> Fuente --> Fuente NDI --> *Nombre* --> *TD-NDI-out*
```

De esta manera podes stremear desde OBS y modificar el stream de acuerdo a los mensajes que los usuarios envien a través del chat de Twitch.

### Créditos 💳

La configuración inicial del operador de WebSockets está inspirado en el tutorial de [Interactive & Immersive](https://interactiveimmersive.io/blog/content-inputs/twitch-chat-in-touchdesigner/).

👋 *Si lo usas, si tenés algún tipo de feedback o problema, hacemelo llegar por favor :)*

---

`EN`
This is a component for [TouchDesigner](https://derivative.ca/) to receive and filter chat messages from a [Twitch](https://www.twitch.tv/) stream.
The `TDTwitch.tox` component filters messages in real time thanks to [WebSockets](https://developer.mozilla.org/es/docs/Web/API/WebSockets_API). It also has the functionality to control the video output (screen capture, webcam, etc) using [NDI](https://www.ndi.tv/tools/) and [OBS Studio](https://obsproject.com/es/download). Both functionalities work independently.
> 💡 Note: due to an incompatibility in OBS v28, in order to use the video functionality you'll need to install [OBS Studio v27.2.4](https://github.com/obsproject/obs-studio/releases/tag/27.2.4) or earlier.


### Recommendation 🚧
It's recommended to download [OBS Studio](https://github.com/obsproject/obs-studio/releases/tag/27.2.4) and sync it to your Twitch account beforehand, so you can test the component from the OBS chat, without the need to stream content and do live testing.

```
# open OBS Studio
PANELS --> CHAT
```

### Quick integration and implementation of the message filter 🚩 

Simply drag the `.tox` file into the project you are working on.
To connect to the Twitch IRC infrastructure you need to fill in your own information in the `Settings` tab.

- `OAuth Token`: log-in to Twitch and then generate the token at [https://twitchapps.com/tmi/].
	> 💡 Note: it's recommended not to share or publish the token to maintain the security of the account.
- `Nickname`: this is the name of your username on [Twitch](https://www.twitch.tv/).
- `Channel`: this is the name of the [Twitch](https://www.twitch.tv/) channel you want to connect to.

Once configured, you should be able to start listening to incoming messages.
> Note: if this does not happen, turn the component off and on or press restart.

`Network Address` and `Network Port`: should remain the same by default and should not be touched, unless they change something in the Twitch infrastructure.

`Keyword`: letter or keyword to choose which messages are filtered. The default is `!`. If you want to filter all messages, you need to leave it empty.

The rest of the parameters can be modified as you wish.

### Quick integration and implementation with NDI and OBS 🎛

In case you want to have control also of the visual part of the stream, it's possible to manage this from TouchDesigner.

1. Install [OBS Studio v27.2.4](https://github.com/obsproject/obs-studio/releases/tag/27.2.4).
	> E.g. on Windows --> `OBS-Studio-27.2.4-Full-Installer-x64.exe`.

2. Install [NDI Tools](https://www.ndi.tv/tools/).

3. Install [obs-ndi v4.9.1](https://github.com/Palakis/obs-ndi/releases/tag/4.9.1)
	> E.g.: on Windows --> `obs-ndi-4.9.0-Windows-Installer.exe`.

4. Open the NDI application and select NDI Screen Capture.

5. Configure with your input devices.

To connect to OBS Studio via NDI you need to go to the `Video` tab in the `TDTwitch` component.
**In** `Active`: ON.
`Source Name`: Choose your configured input device (screen capture, webcam, etc).

**Out** `Active`: ON.

Once configured, you should see video input.
> 💡 Note: in case this does not happen, check the NDI settings.

The rest of the parameters modify them as you like.

Then, in OBS Studio:

```
Add --> Source --> NDI Source --> *Name* --> *TD-NDI-out*
```

This way you can stream from OBS and modify the stream according to the messages that users send through the Twitch chat.

### Credits 💳

The initial configuration of the WebSockets operator is inspired by the [Interactive & Immersive](https://interactiveimmersive.io/blog/content-inputs/twitch-chat-in-touchdesigner/) tutorial.


👋 *If you use it or if you have any feedback or problem, please let me know :)*

🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑🪑
# Configuración de Sistemas de Telefonía



## Pasos para configurar Grandstream

### En BASIC SETTINGS:
- Configurar IP Address
- Configurar Unconditional Call Forward to VOIP. Se pone el User ID (cualquiera?) @ Sip Server (dirección del FreePBX) : Sip Destination Port (5060 por default)
- Dar clic en Update

### En FXO PORT:
- Configurar Primary SIP Server
- Configurar SIP User ID y Authenticate ID (van lo mismo)
- SIP Registrarion: No, porque vamos utilizarlo como troncal
- Enable Current Disconnect: No
- Enable PSTN Disconnect Tone Detection: Yes
- Number of Rings: 3
- Wait for Dial-Tone: No
- Stage Method (1/2): 1. De 1 o 2 etapas, de 1 manda el número directamente; de 2 hace una aunteticación
- Le damos clic en Apply y luego Reboot

## Pasos para configurar FreePBX

### Add SIP Trunk

- Agregamos una nueva troncal SIP la parte de Trunk
- En General, solo ponemos el nombre
- Luego en pjsip Settings -> General, ponemos los mismo en username y Auth username
- Configuramos SIP Server (dirección del dispositivo Grandstream) y Port (distinto al del Grandstream)
- En pjsip Settings -> Advanced, Contact User: el mismo username, From Domain: Grandstream IP, From User: mismo username (se lo va a mandar a sí mismo?)

### Outbounds Routes

- Se selecciona el SIP Trunk que se acaba de crear

## Conceptos

### FreePbx
GUI de código abierto sobre web basado en Asterik, un servidor de VOIP

### PBX
Central telefónica virtual​ conectada directamente a la red pública de telefonía por medio de líneas troncales

### VOIP
Voz sobre protocolo de internet. Telefonía análoga -> IP

### Grandstream HT813
Adaptador de teléfono analógico

### SIP
Session Initiation Protocol. Protocolo de señalización por IP

### PSTN
Red tradicional de telefonía fija

### FXO

Foreign Exchange Office es una interfaz que conecta dispositivos de telefonía analógica a una red telefónica pública (PSTN).

### pjsip
PJSIP proporciona una pila SIP completa, junto con otros componentes para construir aplicaciones de comunicación


# Línea de la vivienda (Kiosco)

Este repositorio contiene la página de internet (static site) de 11ty que abre el dispositivo con bocina de la Línea de la vivienda.

## Configuración

### Configurar wi-fi en el dispositivo

Instrucciones completas: https://www.raspberrypi.org/documentation/computers/configuration.html

Crear archivo: `wpa_supplicant.conf`

```
sudo nano /etc/wpa_supplicant/wpa_supplicant.conf
```

Con el siguiente contenido:

```
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1
country=MX
network={
    ssid="RED"
    psk="CONTRASEÑA"
}
```

### Autostart con Chromium

Después de instalar Chromium, crear un archivo de autostar:

```
nano /home/pi/.config/lxsession/LXDE-pi/autostart
```

Con el siguiente contenido:

```
@chromium-browser --kiosk --incognito --autoplay-policy=no-user-gesture-required https://ldlv-kiosk.netlify.app
@unclutter -idle 0.1 -root
@amixer set PCM 50%
```

### Rotar la pantalla

Instrucciones: http://www.lcdwiki.com/3.5inch_RPi_Display#How_to_rotate_the_display_direction

```
cd LCD-show/
sudo ./rotate.sh 90
```

### Configurar audio

Instrucciones: https://retropie.org.uk/docs/Sound-Issues/#using-a-usb-audio-device
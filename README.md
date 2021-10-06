# Línea de la vivienda (quiosco)


## Set up wifi on Raspberry Pi
Instructions: https://www.raspberrypi.org/documentation/computers/configuration.html

sudo nano /etc/wpa_supplicant/wpa_supplicant.conf

ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1
country=MX
network={
    ssid=""
    psk=""
}
## Chromium autosart for Raspberry Pi
nano /home/pi/.config/lxsession/LXDE-pi/autostart
@chromium-browser --kiosk --incognito --autoplay-policy=no-user-gesture-required https://ldlv-kiosk.netlify.app
@unclutter -idle 0.1 -root

## Rotate screen
Instructions: http://www.lcdwiki.com/3.5inch_RPi_Display#How_to_rotate_the_display_direction
cd LCD-show/
sudo ./rotate.sh 90
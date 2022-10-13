# Corne Keyboard
Info for configuring and setting up the Corne keyboard.        

## Firmware 

### QMK Configurator
Github [Repository](https://github.com/qmk/qmk_configurator)       
Config [File](./Files/CorneKb.json)      

#### Local with docker
``` bash
$ docker run -p 8080:80 qmkfm/qmk_configurator:latest
```
### Layer 0      
![Layer 0](./Img/layer0.jpg)

### 
1. Upload the JSON config file (# QMK config file .json)
2. Push compile button 
3. Dowload HEX file
4. Flash hex to keyboard(See #Flashing)
+ Press reset and then: (8 sec window time)
```bash
$ sudo avrdude -p atmega32u4 -P /dev/ttyACM0 -c avr109 -U flash:w:contra.hex
```
* Modify "corne.hex" with desired filename
* Toolchain needed:  Avr-gcc. [Archwiki](https://wiki.archlinux.org/title/AVR#Toolchain)



# Further Documentation
[QMK](https://docs.qmk.fm/#/newbs_learn_more_resources)         
[thomasbaart.nl](https://thomasbaart.nl/category/mechanical-keyboards/firmware/qmk/qmk-basics/)     


# Other debugging tools
## Libinput
+ List devices and example
``` bash
$ sudo libinput list-devices 
$ sudo libinput debug-events  --device /dev/input/event3
```
## Xinput
``` bash
$ xinput list
$ xinput test 9  
```

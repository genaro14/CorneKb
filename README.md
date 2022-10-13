# Contra Keyboard
Info for configuring and setting up the Contra keyboard.        
![kb](./Img/kb_small_web.jpg)

## Desing Files: 
Ai03: PCB [Link](https://github.com/ai03-2725/Contra)        
Ai03: Case [Link](https://github.com/ai03-2725/ContraPlates)

 # Programing the keyboard

 ## Firmware 

### QMK Configurator
Github [Repository](https://github.com/qmk/qmk_configurator)       
Web [site](https://config.qmk.fm/#/contra/LAYOUT_planck_mit)     
Config [File](./Files/qmk_contra_custom.json)      

#### Local with docker
``` bash
$ docker run -p 8080:80 qmkfm/qmk_configurator:latest
```
### Layer 0      
![Layer 0](./Img/layer0.jpg)

### Layer 3
![Layer 3](./Img/layer3.jpg)

### Layer 4  
![Layer 4](./Img/layer4.jpg)

### Layer 6  
![Capa 6](./Img/layer6.jpg)



### 
1. Upload the JSON config file (# QMK config file .json)
2. Push compile button 
3. Dowload HEX file
4. Flash hex to keyboard(See #Flashing)


### KBFirmware

https://kbfirmware.com/     
Cargar layout contra.json y descargar HEX.      
Config [File](./Files/kbf_contra.json)

## Flashing:
+ Press reset and then: (8 sec window time)
```bash
$ sudo avrdude -p atmega32u4 -P /dev/ttyACM0 -c avr109 -U flash:w:contra.hex
```
* Modify "contra.hex" with desired filename
* Toolchain needed:  Avr-gcc. [Archwiki](https://wiki.archlinux.org/title/AVR#Toolchain)

# Case 
[On Thingiverse](https://www.thingiverse.com/thing:5162848)        
[This Repo](./Case/)         

## Layout

http://www.keyboard-layout-editor.com/#/




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
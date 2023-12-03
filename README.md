# Clean-Square
This is a mod to change the LCD and web UI of a Waveshare 1.3" lcd hat running pwnagotchi
-------------- 
I do not have a pisugar/ups, gps, rtc, etc. so this UI is not optimized for the display of plugins such as clock, battery level, etc. I Might get the hardware and update this later.

minor error on boot, This is just a fork and not an entire rework of the code, so this error still occurs since we are not using a background image.
```
[WARNING] non fatal error while updating view: dictionary changed size during iteration
```
- change this file for the modification of LCD screen  (for ST7789)
```
/usr/local/lib/python3.9/dist-packages/pwnagotchi/ui/hw/libs/waveshare/lcdhat/epd.py  
```
- change this file for modification of web UI  
```
/usr/local/lib/python3.9/dist-packages/pwnagotchi/ui/web/__init__.py
```
- change for file the preview image dimension and position from the web UI  
```
/usr/local/lib/python3.9/dist-packages/pwnagotchi/ui/web/static/css/style.css  
```
  
- options inside the /etc/pwnagotchi/config.toml  
```
ui.display.enabled = true
ui.display.type = "lcdhat"
ui.display.color = "lime" #experiment with colors like cyan, blue, red
ui.display.rotation = 0
ui.display.darkmode = true
ui.display.bg = false
ui.display.bg_path = "/home/pi/img/null.png"
ui.display.hi-res = true

main.plugins.age.enabled = true
main.plugins.age.age_x_coord = 0
main.plugins.age.age_y_coord = 32
main.plugins.age.str_x_coord = 67
main.plugins.age.str_y_coord = 32

main.plugins.exp.enabled = true
main.plugins.exp.lvl_x_coord = 0
main.plugins.exp.lvl_y_coord = 81
main.plugins.exp.exp_x_coord = 38
main.plugins.exp.exp_y_coord = 81
main.plugins.exp.bar_symbols_count = 12
```
  
- change these files for the main interface positions and design
```
/usr/local/lib/python3.9/dist-packages/pwnagotchi/ui/hw/base.py
/usr/local/lib/python3.9/dist-packages/pwnagotchi/ui/hw/lcdhat.py
/usr/local/lib/python3.9/dist-packages/pwnagotchi/ui/components.py
```  

- all custom position values inside plugins  
inside: /usr/local/lib/python3.7/dist-packages/pwnagotchi/plugins/default/  
memtemp.py  
bt-tether.py
exp.py
age.py
  
   

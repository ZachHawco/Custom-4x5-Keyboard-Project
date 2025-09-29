# Customizable 4x5 Keyboard Project, "MacroDuino", Made by Zachary Hawco 
<img width="200" height="128" alt="image" src="https://github.com/user-attachments/assets/4ffbbc61-2234-411a-845a-f482de129d59" />


This is the process of making my custom keyboard project. This repository also contains the key layout firmware I used, GERBER files for the custom PCB, STL files for the custom case, and a download link to the firmware used (QMK Toolbox).

# The start

This project started at the beginning of semester 2. I had originally bought 5 custom circuit boards to build a custom 4x10 keyboard for my school project in my computer engineering class. I only needed 2, the other 3 had just been sitting on my dresser with no purpose, just spare materials. 

<img width="100" height="69" alt="image" src="https://github.com/user-attachments/assets/429382e3-420a-43ae-936a-09e3b22944b2" /> <img width="100" height="78" alt="image" src="https://github.com/user-attachments/assets/a0efe6a0-e1dd-4500-aa3d-f945c048605e" /> x2

The 4x10 keyboard project went pretty well, but the whole thing could have been much more optimized, which is where my idea came in. I was going to build another keyboard, a 4x5 keyboard all by myself, no help involved. 

# Purchases

To start off, I needed some switches. My previous keyboard had used blue switches, so I wanted to experiment with red switches. I heard they sounded a lot smoother and had less response time than blue switches, so I bought a bunch off AliExpress for very cheap. Then, I came up with the idea of LEDs, which can be soldered to pads on the circuit board. I hadn't done anything related to soldering these kinds of LEDs before, SK6812 mini-E RGB LEDs to be exact. My knowledge on how they worked was very little, I conducted a fair bit of research to strengthen my knowledge so I'd be more comfortable when starting with the LEDs. I bought a bunch of them off AliExpress for very cheap. 

<img width="312" height="68" alt="image" src="https://github.com/user-attachments/assets/4d3edc1f-a74b-43a5-8688-b81a15b27c3e" /> <img width="136" height="122" alt="image" src="https://github.com/user-attachments/assets/2316c705-f987-41cd-aa00-d7171133b2cb" /> <img width="172" height="122" alt="image" src="https://github.com/user-attachments/assets/e43f69eb-45ab-422d-9fe5-1de670a2bea0" />

# 3D Case

For this keyboard, I wanted a much better case than the previous one I designed for my school keyboard project, that one was very messy. The walls were WAY too thick, the hole at the bottom for the Arduino was uncentered with the actual Arduino, the switch holder wasn't very centered with the actual case and the bottom slab to cover the Arduino was hot glued on. The slab being hot clued on caused there to be a bit of room between the slab and the case itself, which looked pretty odd from the outside. 

<img width="2071" height="396" alt="image" src="https://github.com/user-attachments/assets/93d372d9-89c8-450f-83fa-62789a061712" />

I spent a lot of time learning about 3D designing, mainly, I learned how to center objects when designing. This would help me with multiple things, I was able to perfectly shape the case so it perfectly fit around the switch holder. By learning about centering, I was also able to properly center the hole in the case for the Arduino to be placed in. The case seemed VERY optimized, almost perfect. I had also learned about connectors in 3D designs. I wanted to have connectors on the bottom slab which would go into holes at the bottom of the case. My intention with this was so the slab would be attached to the case, no room in between, and would also be detachable rather than hot glued. I had been designing the case while I was waiting for the switches and LEDs.

<img width="273" height="173" alt="image" src="https://github.com/user-attachments/assets/6535caf6-ccd1-427f-890b-12e4cbd67467" /> <img width="273" height="173" alt="image" src="https://github.com/user-attachments/assets/4e2cfd2d-f7ad-4225-a9be-ceccf86788ac" />



# Prep

I ended up having some spare time due to the LEDs and switches taking forever to arrive. I used this time to solder the diodes as well as the Arduino onto the circuit board, I also got the custom case 3D printed by my friend Nathan. Once the switches had arrived, I placed all 20 of thm into the switch holder, which was also 3D printed by Nathan during the time I spent waiting for the switches and LEDs to arrive. All the switches fit perfectly into the switch holder, and the switch holder itself fit perfectly into the keyboard case, all thanks to my new knowledge of 3D printing. 

<img width="200" height="130" alt="image" src="https://github.com/user-attachments/assets/d194020f-637f-40f1-9242-cdf3d358f850" />


# Beginning - LEDs

After the switches and LEDs arrived, I began the main portion of the soldering. I started with the LEDs. I did this because they had to be below the switches, so the colours could shine through the clear parts of the switches. This was much more difficult than my previous soldering tasks, the solder pads for the LEDs were very small. I ended up damaging 1 out of 80 of the LED soldering pads (1 LED had to be soldered to 4 different tiny pads on the circuit board), this meant that I would have 1 faulty LED. This task took quite a while, but once I completed it, I moved on to the switches. 

<img width="200" height="100" alt="image" src="https://github.com/user-attachments/assets/d6b38555-de84-4e39-8743-ee09ec3f025c" />


# Switches

This task was much easier, the switches snapped into the circuit board and were all aligned perfectly, thanks to the switch holder. I just had to solder a total of 40 switch pins to the circuit board, 2 on each switch. After soldering all the switches on, the keyboard was pretty much complete, I just needed to upload firmware then glue the switch holder to the case. 

# Firmware

The firmware was quite simple, it's possible to code with Arduino IDE but I used QMK Toolbox to flash the Arduino with key layout firmware. Once QMK Toolbox was downloaded on to my computer, I had to install some drives to support the chips used on the Arduino (ATmega32U4). Then, there's a section to select the chip type, once again beging ATmega32U4. And lastly, you must select the .hex file containing the key layout firmware. Now all that was needed to be done was flash the firmware on to the Arduino. To do this, the Arduino must first be in bootloader mode. I did this by bridging the RST (Reset) and GND (Ground) pins on the Arduino, which you can do with a small metal wire. Once it enters bootloader mode, you will see that the Arduino has been connected to QMK Toolbox. I simply pressed the button on the QMK Toolbox GUI labled "Flash", and it sent the key layout file to the Arduino. Now, when I plugged my USB-C cable into the Arduino, connected to my computer, I was able to use the keyboard as intended.  

# Troubleshooting and Sadness

I noticed the LEDs weren't working, the keys still worked perfectly fine though. I started by doing research online. This keyboard had been built already online, I used tutorials for it for the school project, but this time, I did it all myself. I tried doing the exact thing they had done to get the LEDs working, they used different firmware to set the LED pattern. This was done by plugging the keyboard in, and using the website's firmware to customize the LEDs. I encountered another problem in doing this, my custom keyboard wasn't getting detected as a keyboard. To access the website's firmware, you first had to select the keyboard you would be editing, and it didn't detect mine. I kept changing USB ports on my computer, and kept encountering the same issue. I even used a different USB-C cable, and still nothing. I did some more research but nothing was helpful. I ended up giving up on the LED idea, it was definitely possible but I didn't really need them, especially since I wasn't using clear keycaps so barely any light would shine through. Me also damaging one of the LED pads on the circuit board may have also been the problem. 

# Assembling 

Now that the keyboard was ready, I hot glued the corners of the switch holder/circuit board to the corners of the inside of the case. The Arduino was perfectly centered with the hole in the case for connecting the Arduino and all the switches looked perfectly centered in the case. Since I wanted it to be customizable, I was hoping for the bottom slab to be easily detachable. This would allow me to bridge to 2 pins whenever I wanted to to flash new key layout firmware on to the keyboard. BUT, the connectors I used in my design were connectors that weren't intended to be removed once connected. After connecting the slab to the case, I realized this issue. The slab was so tightly connected to the case. Taking the slab off required quite a bit of force, and in doing so I accidentally broke off 1 of the 4 connectors, since it was so stuck into the case. The circuit board was already hot glued into the case, so it would be a very tedious process to remove it if I wanted to redesign the case. I just went witb it, I reattached the slab, only having 3 connectors attached to the case, with some hot glue used for the broken one. 

# Further Improvement and Completion

I'm overall pretty happy with how it all turned out, especially since it was all done on my own. For future improvements, I could possibly do more research and be more careful when soldering the LED pads. I can be more careful by using a smaller solder tip. I also think I could've found a better solution to the connectors. Most of the connectors in the 3D designing software I used weren't meant to be used to be detachable. I could have used screws, which would require some more research as I have never made anything involving screws. 



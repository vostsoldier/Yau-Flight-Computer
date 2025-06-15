---
title: "Yau Flight Computer"
author: "Peter Park"
description: "A extra extra compressed flight computer with a STM32F405RGT6!"
created_at: "2025-06-12"
---


# June 12th: Started the schematic, and picked out the basic peripherals and parts.

After making my idea, I decided to start on the PCB. I picked out the STM32F405RGT6 for its compactness and power!
A couple of sensors were also helpful, such as BMI088, which was my main IMU, the IIS2MDCTR, which was the magnetometer,
and the BMP388, for my barometer. I started on making the core MCU work, such as adding crystals, decoupling caps, and
other requirements that were needed. 

After I finished wiring the schematic, and used the STM32CubeIDE to find my pins, I now worked on the USB B micro connector! 
For me, the USB B schematic was the hardest part, as I had to reference three different schematics just to make it work reliably... In the end, I got to work, by using a really common ESD connector, USBLC6-2SC6, and the CH

Time spent this session: 5 hours.

# June 13th: Finished power reg/supply, memory, EEProm and reset/boot switches.

Yesterday was a bit tiring, so I did some simple things today. I used the simple but reliable LD39200PU33R to help control the VCC power supply. This was fairly simple, as I just needed to follow the manufacturer's schematic, and add a filtering cap. 

Next, I tackled the EEprom, which wasn't too difficult as well. I was thinking about creating a seperate I2C pinout, but I decided against it, and reused the I2C used by the sensors. 

The memory was a pretty standard layout, with the manufacturer's standard schematic, and connected relevant pins.

Finally, I tackled the switches, which weren't as important, but since they were still a essential function, I did them. 
I quite literally just used the TDD01H0SB1R for both the BOOT switches, and made both of them the same, with just different pins. Heehee! The NRST switch required 4 pins, so I used SKRPANE010. I had to keep in mind that the switches could not be big, as I needed to make this device compact as possible.

Time spent this session: 4 hours.

# June 14th: Finished up the schematic and placed parts in the PCB editor.

Looking at my checklist, I saw that I had some easy parts left to connect. 
I still had my PWM driver+PWM Power, which was incredibly important for my servos, a couple of connectors for UART, I2C and Timers, and some LEDs for visual feedback. 

The PWM driver was pretty straight forward, and I used I2C for controlling it. PWM power was also in a similar fashion, but without any I2C needed. 

I used the STM32CubeIDE to check what pins were avaliable for my various connectors, and I used the most closest/avaliable ones. 

The LEDs were fun to make, as it was a blast deciding the colors! A simple input to GND connection was all I needed, easy peasy!

Time spent this session: 3 hours.

# June 15th: Finished Design rules and started routing.

Good morning! I woke up with an interesting but important thought. Who should I use to make my PCB. I checked on the parts sourcing portion of the Highway website, and I saw PCBway as the preferred vendor. Thankfully, PCBway has a Kicad file just for design rules, so I just downloaded, and drag and dropped! 

Yesterday's progress was immensely helpful, as I just needed to route everything. I decided to start on the front copper layer, as it would be the biggest routes to tackle. 

I decided to do my copper pours last, so I would have to keep adjusting them for every route I do. 

I used really big traces for all the power, especially the PWM Power driver, and medicore traces for the signals. I had to use alot of vias, since this was a space constrained board, so please excuse the amount of holes on there...

I made plated mounting holes, which added some aesthetics, as well as a way to connect my ground pins without using too much vias/tracks. 

Time spent this session: 6 hours.
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
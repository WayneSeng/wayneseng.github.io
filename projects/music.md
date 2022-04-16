---
layout: post
title: Music with Computer Hardware
---

<style>
        figure {
            text-align: center;
        }
</style>

\
Thanks to [Paweł Zadrożniak](https://www.youtube.com/channel/UCximsD7EJ38jzCNgfP_YTmA), [Device Orchestra](https://www.youtube.com/c/DeviceOrchestra), [MrSolidSnake745](https://www.youtube.com/c/MrSolidSnake745), [ArcAttack!](https://www.youtube.com/user/arcattackmusic), [Franzoli Electronics](https://www.youtube.com/c/FranzoliElectronics), and many other smaller creators for inspiration and ideas for this project. This blog may not even have existed if these awesome people didn't exist. Please check out their content and subscribe.
\
\
Making sounds with stepper motors is nothing new. If you own a 3d printer with no silent stepper driver(A4988), you will already be familiar with this. What if we managed to control the exact frequency of these sounds by pulsing the motors at a specific interval(440 times a second)? This is exactly what is happening and is the fundamental building block to tone generation with any electronic device with a stepper motor.
\
\
A floppy drive has a stepper motor that moves the read/write head back and forth along the magnetic tape on the floppy drive. Do you remember those noisy devices? What if we could somehow control the speed of the read/write head? Well we are in luck! If we take a look at the pinout of a floppy drive:
\
![Floppy Drive Pinout](/images/floppy_pinout.png){:.centered}
\
We notice 2 pins of interest called Step and Dir. These 2 pins allow direct control of the speed and direction of the read/write head. Unfortunately, before we can do anything, the drives must be enabled by pulling the Drive select A or B pin to ground. If the green LED on the front of the drive is on, the drive has been enabled. Now if we connect the step pin to ground, the stepper head moves a bit. By connecting the dir pin to high and ground, we can vary the direction of the read/write head. To power the drives, connect a suitable 5v power supply that can deliver at least 500mA to the +5v and GND on the floppy power connector. A computer ATX power supply with a floppy connector can also be used. A microcontroller interprets MIDI data from a computer and drives the floppy drives accordingly.
\
\
Here is a demonstration of 2 floppy drives playing Carra Mia Addio from Portal 2:
\
[![Thumbnail](https://i.ytimg.com/vi/mtVKBj7uICo/maxresdefault.jpg)](https://www.youtube.com/watch?v=mtVKBj7uICo&ab_channel=WayneSeng "Carra Mia Addio on Floppy Drives")
\
Driving stepper motors follows the exact same concept, although an external driver is used. I chose the A4988. The A4988 also has a Step and Dir pin just like the floppy drive. A stepper motor is different from a standard dc motor because it allows so much more control over the exact position of the motor. This allows it to be used in industrial applications such as robot arms or 3d printers as these motors can be controlled with extreme precision.

<figure>
    <img src="/images/stepper_motor.bmp" alt="stepper" width="400"/>
    <figcaption>Bipolar Stepper Motor</figcaption>
 </figure>
\
The A4988 is a complete microstepping motor driver with built-in translator for easy operation with minimal control lines. Carriers with these driver chips can be picked up quite cheaply on Aliexpress. If we take a look at a typical connection diagram, the only two connections to the microcontroller are the DIR and STEP pins. However, it is important to add a decoupling capacitor of approximately 47uF between Vmot and GND. The reset and sleep pins must be connected together to enable the driver. Additionally, the enable pin can be connected to the microcontroller to disable the driver when needed. The A4988 is a microstepping driver, so we can operate in full, half, quarter, eighth, or sixteenth step resolution. From my experience, running the driver at half step resolution for music allows for higher notes to be achieved, as well as less vibration.

<figure>
    <img src="/images/a4988.bmp" alt="stepper" width="400"/>
    <figcaption>A4988</figcaption>
 </figure>

 <figure>
    <img src="/images/A4988_connection.bmp" alt="A4988_schematic" width="600"/>
    <figcaption>Typical Connection Diagram</figcaption>
 </figure>
\
Here is a demonstration of a single stepper motor playing Yakety Sax:
\
[![Thumbnail](https://i.ytimg.com/vi/IOzDmH98lQA/maxresdefault.jpg)](https://www.youtube.com/watch?v=IOzDmH98lQA&ab_channel=WayneSeng "Yakety Sax on Stepper Motor")

## Project Update April 15, 2022

A couple weeks ago, I received the custom PCBs for my ESP32 stepper and floppy synth. I also scavanged a free printer someone had thrown out. Similar to what the floppotron does with flat bed scanners, I will interface with the stepper motor inside the printer scan bed using the L298N H bridge driver. Im glad this printer has been saved from the landfill and will have a new purpose.

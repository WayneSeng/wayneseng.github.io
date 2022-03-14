---
layout: post
title: Music with Computer Hardware
---

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
We notice 2 pins of interest called Step and Dir. These 2 pins allow direct control of the speed and direction of the read/write head. Unfortunately, before we can do anything, the drives must be enabled by pulling the Drive select A or B pin to ground. If the green LED on the front of the drive is on, the drive has been enabled. Now if we connect the step pin to ground, the stepper head moves a bit. By connecting the dir pin to high and ground, we can vary the direction of the read/write head. To power the drives, connect a suitable 5v power supply that can deliver at least 500mA to the +5v and GND on the floppy power connector. A computer ATX power supply with a floppy connector can also be used.
\
Here is a demonstration with 2 floppy drives playing Carra Mia Addio from Portal 2:
\
[![Thumbnail](https://i.ytimg.com/vi/mtVKBj7uICo/hqdefault.jpg)](https://www.youtube.com/watch?v=mtVKBj7uICo&ab_channel=WayneSeng "Carra Mia Addio on Floppy Drives")

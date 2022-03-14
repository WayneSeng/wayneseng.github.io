---
layout: post
title: Music with Computer Hardware
---

img.centered {
display: block;
margin-left: auto;
margin-right: auto;
}
\
Thanks to [Paweł Zadrożniak](https://www.youtube.com/channel/UCximsD7EJ38jzCNgfP_YTmA), [Device Orchestra](https://www.youtube.com/c/DeviceOrchestra), [MrSolidSnake745](https://www.youtube.com/c/MrSolidSnake745), [ArcAttack!](https://www.youtube.com/user/arcattackmusic), [Franzoli Electronics](https://www.youtube.com/c/FranzoliElectronics), and many other smaller creators for inspiration and ideas for this project. This blog may not even have existed if these awesome people didn't exist. Please check out their content and subscribe.
\
\
Making sounds with stepper motors is nothing new. If you own a 3d printer with no silent stepper driver(A4988), you will already be familiar with this. What if we managed to control the exact frequency of these sounds by pulsing the motors at a specific interval(440 times a second)? This is exactly what is happening and is the fundamental building block to tone generation with any electronic device with a stepper motor.
\
\
A floppy drive has a stepper motor that moves the read/write head back and forth along the magnetic tape on the floppy drive. Do you remember those noisy devices? What if we could somehow control the speed of the read/write head? Well we are in luck! If we take a look at the pinout of a floppy drive:
![Floppy Drive Pinout](/images/floppy_pinout.png){:.centered}

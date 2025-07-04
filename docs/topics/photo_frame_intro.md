# <img src = "../../images/logo_1.png" width="15%" />Digital photo frame

A digital photo frame is an LED device that can display pictures. It's similar to an LCD TV, inasmuch as you can plug in a USB flash drive to the TV port and view the pictures. A photo frame, however, isn't as large as a typical TV. Quite a few digital frames also have speakers, just like TVs do, so that you can view movie clips as well. Unlike a TV, where you must scroll through the pictures manually, a digital photo frame can be configured to display pictures in a continuous loop, advancing to the next picture after a specified time period.

<a href = "../../images/frame_in_action_1.jpeg"><img src = "../../images/frame_in_action_1.jpeg" width="80%" /></a><br/>
<span style="font-size:75%;">To see a larger image, click the image.</span>

This project uses a Raspberry Pi 3B+ computer and a Raspberry Pi Touch Display to make a digital photo frame. To make it all work, you must set up a headless Raspberry Pi computer, connect it to a screen, and then run Python on it. It doesn't matter if you don't know Python, because I'll provide the entire code for you to use. If you do know Python, you can tweak the code to include the enhancements that I'll suggest at the end of the tutorial.

<hr/>

## Materials

For the photo frame:

-  A Raspberry Pi 3B+ computer. This little computer board will hold the code that displays the photos.
-  A Raspberry Pi 7" official touch display. This screen is where the photos are displayed. You can choose to use any other display screen that can be used with a Raspberry Pi 3B+, but I used the official display because it's a plug-and-play set up.
-  A Raspberry Pi official power adapter. Theoretically, any adapter with a USB-C cable that can plug into the Raspberry Pi should work fine. In practice, it's better to get the official power adapter because it's been tested to deliver the exact power that the Raspberry Pi needs.
-  A microSD card. This tiny card will contain the operating system that your Raspberry Pi will run on.
-  A USB drive. This flash drive will contain your photos.
-  (Optional) Heat sinks. These are little metal blocks that draw the heat away from the chips on the Raspberry Pi board. A Python program for this project should not heat the Raspberry Pi too much, but it is safe practice to use heat sinks.
-  (Optional) An external keyboard and a mouse. These two things are optional, because you can use your laptop keyboard and touchpad to issue commands to the Raspberry Pi computer.

To set up the Raspberry Pi:

-  A laptop (or desktop), with a microSD port. If your laptop does not have this port, you need a microSD card reader that you can plug into laptop. After the Raspberry Pi is set up and the photo frame is working, you'll no longer need the laptop.
-  Administrator privileges on the laptop, so that you can download all the required software on it.
-  An internet connection. After the set up is complete, this project does not need an internet connection.

## Steps

To build the photo frame, you first connect the touch display screen to the Raspberry Pi, then make the Raspberry Pi ready by installing an operating system on it, and finally write a script to display your photo collection. A step-by-step guide is at [how to make a digital photo frame](photo_frame_steps.md).

## Cost

All figures are in Indian Rupees (INR), and inclusive of GST (goods and service tax).

| Item | Amount (INR) |
| :---- | -----------: |
| Raspberry Pi 3 Model B | 3,538.82 |
| 12.5W Official Raspberry Pi Micro USB Power Supply | 708.00 |
| Raspberry Pi Official 32GB V3.0 , A2 Class Micro SD | 398.84 |
| Aluminium Heat Sink | 35.40 |
| Official Raspberry Pi 7" Touch Display | 6,372.00 |
| Raspberry Pi 4 Model B Touchscreen 7 inch Display Case -ABS, Black | 849.00 |
| | **11,902.06**|

## Alternatives

This project is not the only way that you can get a digital photo frame up and running on a Raspberry Pi. Here are some alternatives:

-  [PiGallery2](https://bpatrik.github.io/pigallery2/). After you've set up your Raspberry Pi, as descibed in steps 1 through 4 of this project, you must run a server on your Raspberry Pi, and then install and run PiGallery2. See [How to set up Raspberry Pi as a server](https://www.makeuseof.com/set-up-raspberry-pi-as-server/) and [How to install PiGallery2 on Raspberry Pi](https://www.makeuseof.com/how-to-install-and-use-pigallery2-on-your-raspberry-pi/).
- [InkyPi](https://github.com/fatihak/InkyPi). After you've set up your Raspberry Pi, as described in steps 1 through 4 of this project, you must attach the Pimoroni Inky Impression display to the Raspberry Pi, and then install and run [InkyPi](https://github.com/fatihak/InkyPi?tab=readme-ov-file#installation).
- [`imv` package](https://sr.ht/~exec64/imv/). After you've set up your Raspberry Pi, as descibed in steps 1 through 4 of this project, you write a Python script to use the `imv` package, which is a command line image viewer. See [Photo frame at PiMyLifeUp](https://pimylifeup.com/raspberry-pi-photo-frame/).

## Motivation

Why I went in for this project? It's because of a broken photo frame at home. I had gifted the frame to my brother about a decade and a half ago. It has started showing its age: photos displayed with random rainbow stripes or the screen displaying snowshowers intermittently. A search on Amazon revealed that reputed photo companies (such as Sony, Kodak, etc.) no longer made these photo frames. Because I wasn't willing to go with cheaper local alternatives, I had to pull my sleeves up and get into the first ever Raspberry Pi project of my life. With zero knowledge of single computer boards and their workings.
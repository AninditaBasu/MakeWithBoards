## Attach a touch display to the Raspberry Pi board

The Raspberry Pi is what they call an SBC (a single board computer). It has neither a screen where you can see the output of your commands, nor a keyboard through which you can send these commands to the computer. It is just a barebones computer, with no peripheral devices such as keyboard, mouse, monitor, speaker, or microphone. To use a Raspberry Pi as a computer, you must manually attach these peripherals to it. 

Here, you're not going to use the Raspberry Pi as a computer, but you *are* building a photo frame. Therefore, the barest minimum peripheral device that you need is a display screen.

These are the materials that you need.

<table>
<tr>
<th>Front view</th><th>Back view</th>
</tr>
<tr>
<td>
<p style="text-align:center;">
<a href = "../../images/frame_front.jpeg"><img src="../../images/frame_front.jpeg" width="45%" /></a><br/>
<span style="font-size:75%;">To see a larger image, click the image.</span>
</p>
</td>
<td>
<p style="text-align:center;">
<a href = "../../images/frame_back.jpeg"><img src="../../images/frame_back.jpeg" width="45%" /></a><br/>
<span style="font-size:75%;">To see a larger image, click the image.</span>
</p>
</td>
</tr>
</table>

Notice the left side of both the images. At the top left quadrant is the Raspberry Pi board. At the bottom left is the power supply, the heat sinks, and the microSD card. These objects, when put together, constitute a standalone Raspberry Pi computer that you can use to do...stuff. Like building a digital photo frame.

Look at the right half of both the images. The objects there are what's included in an official pack of the Raspberry Pi Touch Display. When plugged into a Raspberry Pi computer (which you can assemble from the materials at the left), this set becomes the display unit for the Raspberry Pi computer. 

Notice the view of the display screen from the back (second image, upper right quadrant).  The green board, called the controller board, has four little screws at the four corners. To mount the display screen on to the Raspberry Pi, you loosen these four screws at the four ends of the controller board of the display screen, place the Raspberry Pi on to it, and put the screws back in place.

You then connect these two boards by means of two wires (red and black) and a cable (the white straight strip), which you can see at the bottom right quadrant of the images. Two things to note here:

-  You don't need the shiny curved strip also shown in the picture; it came as standard packaging with the display and is used in Raspberry Pi 4 models. The model being used here, in this project, is Raspberry Pi 3B+, so the straight white strip is the one to use. In the Raspberry Pi world, strips like these are known as ribbon cables.
-  You also don't need the yellow wire and the green wire. In the Raspberry Pi world, this kind of wire is called a jumper cable. Your photo frame uses a Raspberry Pi 3B+, which needs only two jumper cables, the red and the black. The yellow and green jumper cables are needed only if you're using an older model of the Raspberry Pi, one that does not have a 40-pin GPIO strip. For this tutorial, the GPIO pins aren't the focus so they won't be discussed, but if you're curious, you can read up on `GPIO`, `SCL`, and `SDA` pins.

When you're done with attaching the display screen to the Raspberry Pi, the entire assembly should look something like this image (taken from `https://www.raspberrypi.com/documentation/accessories/display.html`):

<a href = "../../images/display_mounted.png">
<img src="../../images/display_mounted.png" width="50%"/></a><br/>
<span style="font-size:75%;">To see a larger image, click the image.</span>

I found this YouTube video helpful. It shows the steps to attach the display screen to the Raspberry Pi board.

<iframe width="560" height="315" src="https://www.youtube.com/embed/SyhJctufiRI?si=Hv3bjPuczohvv8ES" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

If you'd rather read some written instructions, see this official guide from the good folks at Raspberry Org: [Touch Display](https://www.raspberrypi.com/documentation/accessories/display.html).

After the display screen is mounted on the computer board, fix the heat sinks.

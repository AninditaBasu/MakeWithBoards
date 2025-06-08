#  <img src = "../../images/logo_1.png" width="15%" />Make a digital photo frame

The steps to build the digital photo frame are these:

1. Attach the touch display to the Raspberry Pi board.
1. Attach the heat sinks to the Raspberry Pi board.
1. Prepare your laptop.
1. Download the Raspberry Pi operating system.
1. Install the operating system.
1. Write the Python code that displays the photos.
1. Refine the project.

<a href = "../../images/frame_in_action_2.jpeg">
<img src="../../images/frame_in_action_2.jpeg" width="80%"/></a>
<br/>
<span style="font-size:75%;">To see a larger image, click the image.</span>

<hr/>

{% include 'pi_3b_attach_display.md' %}

<hr/>

{% include 'pi_3b_attach_heatsink.md' %}

<hr/>

{% include 'set_up_laptop.md' %}

<hr/>

{% set pimodel = "Raspberry Pi 3" %}
{% set pios = "Raspberry Pi OS 64-bit (A port of Debian Bookworm with the Raspberry Pi Desktop)" %}
{% include 'install_os.md' %}

<hr/>

{% include 'pi_3b_install_os.md' %}

<hr/>

{% include 'python_photo_frame.md' %}

<hr/>

{% include 'photo_frame_refine.md' %}

<hr/>

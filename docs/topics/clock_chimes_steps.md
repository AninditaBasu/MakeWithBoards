#  <img src = "../../images/logo_1.png" width="15%" />Make chimes on the hour and half hour

The steps to make the chimes are these:

1. Attach the heat sinks to the Raspberry Pi board.
1. Prepare your laptop.
1. Download the Raspberry Pi operating system.
1. Install the operating system.
1. Write the Python code that makes the chimes.

<a href = "../../images/chime_wip.jpeg">
<img src="../../images/chime_wip.jpeg" width="80%"/></a>
<br/>
<span style="font-size:75%;">To see a larger image, click the image.</span>

<hr/>

{% include 'pi_4_attach_heatsink.md' %}

<hr/>

{% include 'set_up_laptop.md' %}

<hr/>

{% set pimodel = "Raspberry Pi 4" %}
{% set pios = "Raspberry Pi OS 64-bit (A port of Debian Bookworm with the Raspberry Pi Desktop)" %}
{% include 'install_os.md' %}

<hr/>

{% include 'pi_4_install_os.md' %}

<hr/>

{% include 'python_clock_chime.md' %}

<hr/>

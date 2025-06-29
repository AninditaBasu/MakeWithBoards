#  <img src = "../../images/logo_1.png" width="15%" />Make a surveillance camera

These are the steps:

1. Prepare your laptop.
1. Download the Raspberry Pi operating system.
1. Install the operating system.
1. Attach the camera
1. Write the bash code that makes the videos.
1. Refine the project.

<a href = "../../images/pi_zero.jpeg">
<img src="../../images/pi_zero.jpeg" width="35%"/></a>
<a href = "../../images/pi_zero_cam.jpeg">
<img src="../../images/pi_zero_cam.jpeg" width="35%"/></a>
<br/>
<span style="font-size:75%;">To see a larger image, click the image.</span>

<hr/>

{% include 'set_up_laptop.md' %}

<hr/>

{% set pimodel = "Raspberry Pi Zero W" %}
{% set pios = "Raspberry Pi OS 32-bit (A port of Debian Bookworm with the Raspberry Pi Desktop)" %}
{% include 'install_os.md' %}

<hr/>

{% include 'pi_zero_install_os.md' %}

<hr/>

{% include 'pi_zero_attach_camera3.md' %}

<hr/>

{% include 'bash_security_camera.md' %}

<hr/>

{% include 'security_camera_refine.md' %}

<hr/>
## Write the Python code for playing the clock chimes

For this clock-chiming project, the job of chiming on the hour and half-hour will be done by a Python program.

The operating system that you installed on the Raspberry Pi already includes Python, as well as an integrated development environment (IDE) that makes it easier for you to write, run, and edit Python programs. This IDE is the Thonny IDE. You'll use Thonny to write the Python program.

1.  Plug in the speaker to the Raspberry Pi, and switch both of them on.
1.  If you don't have an external keyboard or mouse, log in remotely to your Raspberry Pi by using Connect:
    1.  On your laptop, open `https://connect.raspberrypi.com/` and sign in.
	1.  On the Devices page, click **Connect via > Screen sharing**, and wait for a few seconds for the remote session to start. You should then see the Raspberry Pi desktop in your laptop browser window.
1.  Install any patches, fixes, and upgrades that might have been made to the operating system by opening the Raspberry Pi terminal window (the console icon near the top left) and running the following two commands one after the other:
    -  `sudo apt-get update`
	-  `sudo apt-get upgrade`
1.  Open Thonny by clicking the Raspberry Pi icon near the top left, and then clicking **Programming > Thonny**.
{% include 'thonny_venv.md' %}
1.  Open a new file by clicking **File > New**. Copy into it the code from [The code](#the-code) section of this page.
1.  In the same virtual environment, at the same location as the `.py` file, paste a sound file containing the music you want to be played as the chimes. This sound file should be a `.wav` file because the `pygame` library can play only `.wav` files. For this project, I downloaded a royalty-free sound file that had peeling church bells, and then edited the file in to separate out a 2-second clip of a dinging sound.
1.  Install a Python package called `pygame` in the virtual environment. To do so, click **Tools > Manage packages**, search for `pygame`, and click **Install**.
1.  Edit line 7 of the Python code to make sure that the file name is correct. For example, if your sound file is called `dingdong.wav`, line 7 should be `sound_file = 'dingdong.wav'`.
1.  Save the file, and click the **Run** icon. Wait for the half hour or the hour. You should be able to hear the chimes.

<video width="80%" height="80%" controls>
  <source src="../../images/demo_clock_2.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

<hr/>

### The code

```
{% include 'pyscript_clock_chime.py' %}
```
<span style="font-size:75%;">You can also [download the raw Python file](https://raw.githubusercontent.com/AninditaBasu/pi-projects/refs/heads/main/_includes/pyscript_clock_chime.py).</span>

Notice the first three lines of the code.

```
import time
from datetime import datetime
import pygame
```

This is where you import the libraries and packages that are needed for this project. {% include 'python_library.md' %}

Some libraries are included by default in every Python installation. The libraries called `time` and `datetime`, which are imported in the first two lines, are such libraries. Some other libraries are ones that you manually install in the virtual environment of your project. The `pygame` library is one such library. It is a library for handling multimedia files like the sound file you use in this project.

Take a look at this part of the code:

```
time.sleep(2)  # A 2-second delay between chimes
```

This bit specifies a 2-second delay when the chimes are going to be repeated for the number of hours. For example, if it is 4 o'clock, the playing is repeated four times, with a 2-second delay between the repetitions.

Look at how `sleep_time` is calculated. It takes into account the seconds that have elapsed while the sound was playing; therefore, this `sleep_time` is calculated twice, once on the hour and once on the half-hour.

```
sleep_time = (60 - current_minute) * 60 - current_second

...

sleep_time = 30 * 60 - current_second
```

Take a look at this bit, which controls the number of times the chime is played:

```
play_chime(1)

...

play_chime(chime_count)

```

`chime_count` is calculated according to the current hour, as follows: `chime_count = now.hour % 12 or 12`. The reason for using a modulus operation rather than a substraction operation (like `chime_count = now.hour - 12`) is explained in the following table.

|`now.hour`| Modulus (`now.hour % 12`) | Substraction (`now.hour - 12`) | Notes |
|:--------:|:-------------------------:|:------------------------------:|--------|
| 13 | 1 | 1 | Both methods return the correct hour. |
| 14 | 2 | 2 | Both methods return the correct hour. |
| 23 | 11 | 11 | Both methods return the correct hour. |
| 0 (midnight) | 0 | - 12 | Incorrect. Solved by using `or 12` in the modulus operation. |
| 12 (noon) | 0 | 0 | Incorrect. Solved by using `or 12` in the modulus operation. |

Notice the `or` operater in `chime_count = now.hour % 12 or 12`. This code sets the value of the `chime_count` variable to the modulus value, but if the modulus is zero, sets the `chime_count` value to 12.

Now, see this bit near the start of the code:

```
pygame.mixer.init(frequency=44100, size=-16, channels=2, buffer=4096)
```

This code initialises the `pygame` module with the following parameters:
- `frequency`, which is set to match my sound file's sample rate. To find the sample rate of your sound file, run the following command from the Raspberry Pi terminal: `file <filename.wav>`, where `filename.wav` must be replaced by the name of your sound file. You should get an output that's something like this: `RIFF (little-endian) data, WAVE audio, Microsoft PCM, 16 bit, stereo 44100 Hz`
- `size`, which is the bit-depth of the sound file. In my case, because the format is `PCM`, a negative sign (`-16`) is used, which is standard for PCM data. 
- `channels`, which is set to `2` because my audio device is a dual-channel speaker.
- `buffer`, increased from the default of `2048` to remove any stuttering.

You can also do a simpler initialisation, without specifying the parameters, like this: `pygame.mixer.init()`.  But sometimes, doing so might lead to the sound file seeming to stutter on playback due to buffering issues.

### Troubleshooting the code

**1.  `pygame` not found**

If `pygame` does not show up in the search results when you try to install it through **Tools > Manage packages**:

{% include 'thonny_install_packages.md' %}

You should now be able to see `pygame` in the list of installed packages.

**2.  Stuttering playback**

If your sound file plays perfectly on your laptop but seems to be stuttering on the Raspberry Pi computer, the problem might lie with buffering. Increase the buffer size to `8192` or higher when initialising the `pygame` library at line 6.
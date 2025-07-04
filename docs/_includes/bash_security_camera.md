## Write the bash code for the surveillance camera

A surveillance camera continuously records the happenings that it can 'see'. For this project, this job will be done by a bash script.

The operating system that you installed on the Raspberry Pi already includes `libcamera`, which is the package that will be used for recording videos.

1.  Switch on the Raspberry Pi and wait for the green light to stop flashing.
1.  Log in remotely to your Raspberry Pi by using Connect:
    1.  On your laptop, open `https://connect.raspberrypi.com/` and sign in.
	1.  On the Devices page, you should see your Raspberry Pi. If it isn't, wait for a few minutes and refresh the page.  Then, click **Connect via > Screen sharing**, and wait for a few seconds for the remote session to start. You should then see the Raspberry Pi desktop in your laptop browser window.
1.  Install any patches, fixes, and upgrades that might have been made to the operating system by opening the Raspberry Pi terminal window (the console icon near the top left) and running the following two commands one after the other:
    -  `sudo apt-get update`
	-  `sudo apt-get upgrade`
1.  Open a terminal window by clicking the Terminal icon near the top left. At the prompt, go to the `Videos` directory by typing the following command: `cd ~/Videos`. This is the directory that will contain the bash script and the videos.
1.  Open a new file by typing the following command: `nano simplevideo.sh`. The built-in code editor, called `nano`, opens. 
1.  Copy into it the code from [The script](#the-script) section of this page. Then, save the file and exit from the nano editor by doing these steps:
    1.  Press Ctrl + O. The editor displays the name that the file should be saved with. You've already specified it to be `simplevideo.sh`.
	1.  Press Enter. The file is saved.
	1.  Press Ctrl + X. You're taken back to the command prompt.
1.  Turn the bash script into an executable file by typing the following command: `chmod +x simplevideo.sh`.
1.  Run the file by typing the following command: `./simplevideo.sh`. You should start seeing some messages on the screen.

Go to the directory where your videos are being saved (Click the File Manager icon near the top left, right next to the Raspberry Pi icon). To view the video file, double-click the file.

To stop the video recording at any time, in the terminal window, press Ctrl + C. If you see the script automatically start recording again, press Ctrl + C again. (This is expected behaviour. How to handle this behaviour better is explained in the "Refine the project" section.)

<hr/>

### The script

```
{% include 'bashscript_simplevideo.sh' %}
```
<span style="font-size:75%;">You can also [download the code file](https://raw.githubusercontent.com/AninditaBasu/pi-projects/refs/heads/main/_includes/bashscript_simplevideo.sh).</span>

Notice the second line of the script.

```
SAVE_PATH="/home/oracle/Videos"
```

This is where you specify the directory to save the videos to. Replace `oracle` with the user name that you set up the Raspberry Pi with.

Notice the next line:

```
DURATION=$((60 * 1000))  # 1 minute in milliseconds
```

The duration tells the script how long each video should be.

Now look at the last bit:

```
libcamera-vid --nopreview --width 640 --height 480 --bitrate 1000000 --timeout $DURATION -o "$SAVE_PATH/ve_$TIMESTAMP.h264"
```

What's happening here that a video is being saved every 1 minute to the location you specified.

-  `libcamera-vid`: This is part of the Raspberry Pi's `libcamera` stack, and it handles video recording.
-  `--nopreview`: Tells the system not to open a preview window because the script in running in the background in headless mode.
-  `--width 640 --height 480`: Sets the video resolution to 640×480 pixels. A lower resolution means smaller files and faster processing. You could change this to `--width 1280 --height 720` or higher for better quality but doing so uses up more computer resources.
-  `--bitrate 1000000`: Sets the video compression level to 1,000,000 bits per second (that is, 1 Mbps). A higher bitrate means better video quality but larger files. For better visuals, you could increase this to 3000000.
-  `----timeout $DURATION`: This sets how long the video recording lasts in milliseconds. You've already specified the value through the `$DURATION` variable.
-  `-o "$SAVE_PATH/ve_$TIMESTAMP.h264"`: Specifies where to save the video file and with what name. `"$SAVE_PATH"` is a variable holding your directory (for example, `/home/oracle/Pictures`). `ve_$TIMESTAMP.h264` names the file with a timestamp (like `ve_20250420_135030.h264`). `.h264` is the raw video format. You can convert it to `.mp4` if needed.

### Troubleshooting the code

**No output**

If you don't see any `test.jpg` in the `Videos` directory, or if you don't see any messages on the terminal window, it's likely that the `libcamera` package wasn't installed properly. Reinstall it by running the following commands one after the other.

1.  Remove the existing packages: `sudo apt purge libcamera0 libcamera-apps libcamera-ipa libcamera0.4`.
2.  Clean up the cache: `sudo apt autoremove` and then `sudo apt clean`.
3.  Update the package list: `sudo apt update`.
4.  Install everything afresh: `sudo apt install libcamera-apps`.

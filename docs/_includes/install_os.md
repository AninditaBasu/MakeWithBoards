## Download the operating system

For this step, you need a microSD card and a card reader that can be plugged into your laptop.

The operating system will be downloaded on to the microSD card, which will then be inserted into the microSD slot of the Raspberry Pi board, which will then be plugged into a power socket. That's what will get the little board up and running, and make it ready for the final steps of the project.

1. Turn on your laptop. Make sure that it is connected to the internet.
1.  Plug the microSD card into your laptop, and format it by running SD Card Formatter. Use the **Overwrite** option to format; this option takes longer but ensures that everything on the SD card is wiped clean and the card formatted.
1.  On the laptop, run the Raspberry Pi Imager wizard and download Raspberry Pi's operating system to it. All Raspberry Pi computers run on  operating systems that are based on the open-source Debian operating system. This project uses Debian Bookworm with the Raspberry Pi Desktop. Begin the download process by selecting the model as **{{pimodel}}** and the operating system as **{{pios}}**.
1.  On the page for OS customisation, click **Edit settings**. These settings are used for configuring the operating system with your credentials and environment. If prompted for loading Wi-Fi credentials from your host computer, respond in the affirmative. Then, specify the values for at least the following parameters. It's also a good idea to note down these values for easy reference, because you'll need these values later:
    -  On the **General** page:
        -  **hostname**, which is a name you call your Raspberry Pi by. This is the name that'll be displayed when you search for your Raspberry Pi on the network later.
	    -  **username** and **password**, which are the credentials to use when logging in to Raspberry Pi remotely. The user name that you specify here will have administrator privileges to your Raspberry Pi.
	    -  **Wireless LAN**, which should be prepopulated because you already asked the Wi-Fi credentials to be loaded from the host computer.
	    -  **Locale settings**, for your time zone, keyboard preferences, and other such locale-related things.
	-  On the **Services** page, select the **Enable SSH** box and the option for password authentication. Later, when the project is up and running, you might choose to isolate your Raspberry Pi from the network, and if you decide to do that, you can turn SSH off, but for the time being, enable it because you _might_ need it for troubleshooting purposes.
    -  On the **Options** page, select all the options.
1.  Click **Save** and, when prompted for applying these settings, answer in the affirmative. Click **Yes** again, and then wait for the operating system to be copied on to the microSD card.
1.  When the process is complete, take the microSD card out of the laptop port.
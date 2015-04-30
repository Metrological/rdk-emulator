RDK Emulator
============

The RDK Emulator enables you to run Metrological SDK Apps.

Getting Started
---------------

**Requirements**

- Download [NodeJs](https://nodejs.org/) and install it, if absent from your host system.
- Download [VirtualBox](http://virtualbox.org) and install it, if absent from your host system.
- Download [7zip](http://www.7-zip.org/) and install it, if absent from your host system.

*Depending on your host OS do the following:*

- On Linux open console and type "ssh --help". When this command is missing, install this package on your Linux distribution.
- On Mac enable ssh-command (see [how-to-enable-ssh](http://www.maclife.com/article/howtos/how_enable_ssh_your_mac)), if this is not enabled already.
- On Windows download and install [Putty](http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html) and/or [Notepad++](http://notepad-plus-plus.org/), if these are not installed already. 

*Clone the [RDK-emulator](https://github.com/Metrological/rdk-emulator.git)-repository to your host-system*

  `git clone https://github.com/Metrological/rdk-emulator.git` 

*Get source from [Metrological Application Framework SDK](https://github.com/metrological/maf3-sdk) and install dependencies*

  `git clone https://github.com/Metrological/maf3-sdk.git && cd maf3-sdk`

  `npm install` 
 
**Running MAF-SDK inside RDK-emulator**

*Startup node.js with maf3-sdk*

  `NODE_PORT=8080 node sdk.js`

This will startup the server with maf3-sdk interface.

*Import RDK-emulator into VirtualBox*

On Linux or Mac goto the rdk-emalutor-directory and join the four 7zip-parts of rdk-emulator.7z files:

  `cd ../rdk-emulator && 7z x rdk-emulator.7z.001`

Uncompress rdk-emulator.tar.gz file:
  
  `tar xzvf rdk-emulator.tar.gz`

On Windows see [7zip](http://www.7-zip.org/) how to do this.

Import the resulting RDK-emulator.ova into VirtualBox.

In VirtualBox select the RDK-emulator and start it. Wait until the opening-page is visible (you will see the title `Comcast Set-Top-Box-Developer-Edition` at the top of the page).

With the LEFT- or the RIGHT-key, of your host-keyboard, you can navigate, respectively: to the left or to the right. 

Navigate to the purple button, called "DeviceInfo", and select this button by pushing the ENTER-key. You will end-up with a completely white page with only the ip-address of the RDK-emulator displayed on it. Write down this ip-address somewhere (you will need it later). 

By pushing the BACKSPACE-key you will leave the `DeviceInfo`-tabpage and end-up again on the opening webpage. 

Lastly, by selecting `Machine`-menutab and then choosing `Power Down` item in the sub-menu of the `Machine`-menutab you can stop the RDK-emulator. 

Okay, at this stage the RDK-emulator is also up and running. Perhaps a little background information is in order here. During the boot-process of the RDK-emulator, a RDK-webbrowser is started with an initial html-webpage, called menu.html. This file is located at `/opt/www/menu.html`.     

*On Linux or Mac fetch menu.html onto your host system:*
   
  `scp root@<ip-address-of-rdk-emulator>:/opt/www/menu.html menu.html`

On Window see [use ftp-plugin of Notepad++](http://www.thewindowsclub.com/access-ftp-server-notepad) howto do this.

Open menu.html-file in your favourite text-editor and replace the `<ip-address-of-host>` in href="http://`<ip-address-of-host>`:8080" with the ip-address of your host.

*On Linux or Mac copy the changed menu.html back onto RDK-emulator:*

  `scp menu.html root@<ip-address-of-rdk-emulator>:/opt/www/menu.html`

On Window see [use ftp-plugin of Notepad++](http://www.thewindowsclub.com/access-ftp-server-notepad) howto do this.

Reboot the RDK-emulator and select the AppStore-button. You are now in the AppStore created with [maf3-sdk](https://github.com/Metrological/maf3-sdk/).

*Inspecting and debugging the RDK-browser with the WebInspector:*

On your host-system open a webbrowser of your choice and goto the following URL-address.

  `http://<ip-address-of-rdk-emulator>:9222`

You will end-up with a webpage with only one hyperlink on it. By clicking on this link you will end-up with the WebInspector-menu. Developers still new to the WebInspector can check out an [introduction guide](https://developer.apple.com/library/mac/documentation/AppleApplications/Conceptual/Safari_Developer_Guide/Introduction/Introduction.html#//apple_ref/doc/uid/TP40007874-CH1-SW1) for more background information.   

*Create a TV-app yourself:*

Now your TV-app development environment is ready, you have everything in place to develop, build and test a new TV-app yourself. Just jump to [howto create a TV-app](https://sdk.metrological.com/getting-started) for a short introduction.  


-------------------------------

License
-------

Please read and agree with the [LICENSE](https://github.com/Metrological/rdk-emulator/blob/master/LICENSE) before using the RDK Emulator. All OSS licenses can be found at [OSS_LICENSES](https://github.com/Metrological/rdk-emulator/blob/master/OSS_LICENSES).

Contribute
----------

**Would you like to join our team?** Drop your details at recruitment@metrological.com 

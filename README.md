RDK Emulator
============

The RDK Emulator enables you to run Metrological SDK Apps.

Getting Started
---------------

**Requirements**

- Download [NodeJs](https://nodejs.org/) and install it, if absent from your host system.
- Download [VirtualBox](http://virtualbox.org) and install it, if absent from your host system.

*Depending on your host OS do the following:*

- On Linux open console and type "ssh --help". When this command is missing, install this package on your Linux distribution.
- On Mac enable ssh-command (see [how-to-enable-ssh](http://www.maclife.com/article/howtos/how_enable_ssh_your_mac)), if this is not enabled already.
- On Windows download and install [Putty](http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html), [7zip](http://www.7-zip.org/) and/or [Notepad++](http://notepad-plus-plus.org/), if these are not installed already. 

*Get source from [Metrological Application Framework SDK](httpsdd://github.com/metrological/maf3-sdk) and install dependencies*

  `git clone https://github.com/Metrological/maf3-sdk.git && cd maf3-sdk`

  `npm install` 

*Add scale setting to index.html*

Open index.html in the editor-of-choice and just cut-and-paste below the line `language: 'en',`, the following line:

  `scale: 580,`

This will overwrite the default size of the AppStore to this value. So that the AppStore better fits the RDK-emulator. 
    
**Running MAF-SDK inside RDK-emulator**

*Startup node.js with maf3-sdk*

  `NODE_PORT=8080 node sdk.js`

This will startup the server with maf3-sdk interface.

*Import RDK-emulator into VirtualBox*

  `Extract the rdk-emulator.tar.gz and import the rdk-emulator.ova into VirtualBox.`

Select the RDK-emulator in VirtualBox and press start-button in order to boot the emulator. Wait until the opening-page is visible (you will see the title `Comcast Set-Top-Box-Developer-Edition` at the top of the page).

With the LEFT- or the RIGHT-key, of your host-keyboard, you can navigate, respectively: to the left or to the right. Navigate to the purple button, called "DeviceInfo", and select this button by pushing the ENTER-key. You will end-up with a completely white page with only the ip-address of the RDK-emulator displayed on it. Write down this ip-address somewhere (you will need it later). 

By pushing the BACKSPACE-key you will leave the `DeviceInfo`-tabpage and end-up again on the opening webpage. 

Lastly, by selecting `Machine`-menutab and then choosing `Power Down` item in the sub-menu of the `Machine`-menutab you can stop the RDK-emulator. 

Okay, at this stage the RDK-emulator is also up and running. Perhaps a little background information is in order here. During the boot-process of the RDK-emulator, a RDK-webbrowser is started with an initial html-webpage, called menu.html. This file is located at `/opt/www/menu.html`.     

*On Linux or Mac fetch menu.html onto your host system:*
   
  `scp root@<ip-address-of-rdk-emulator>:/opt/www/menu.html menu.html`

On Window see [use ftp-plugin of Notepad++](http://www.thewindowsclub.com/access-ftp-server-notepad) howto do this.

Change the existing href="http://widgets.metrological.com/metrological/nl/rpi" into href="http://`<ip-address-of-host>`:8080" in menu.html-file.

*On Linux or Mac copy the changed menu.html back onto RKD-emulator:*

  `scp menu.html root@<ip-address-of-rdk-emulator>:/opt/www/menu.html`

On Window see [use ftp-plugin of Notepad++](http://www.thewindowsclub.com/access-ftp-server-notepad) howto do this.

Reboot the RDK-emulator and select the AppStore-button. You are now in the AppStore created with [maf3-sdk](https://github.com/Metrological/maf3-sdk/).

Finally, goto [howto create an app](https://sdk.metrological.com/getting-started) for a short introduction for creating an app.  


-------------------------------

License
-------

Please read and agree with the [LICENSE](https://github.com/Metrological/rdk-emulator/blob/master/LICENSE) before using the RDK Emulator. All OSS licenses can be found at [OSS_LICENSES](https://github.com/Metrological/rdk-emulator/blob/master/OSS_LICENSES).

Contribute
----------

**Would you like to join our team?** Drop your details at recruitment@metrological.com 

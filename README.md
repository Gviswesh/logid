# LOGI D For Linux

## AIM
The thought behind creating this repository is to help people who run Linux and own a Logitech multi button mouse. This configuration file was created for Logitech MX Master 3 and was tested in Surface Laptop 3 running on Arch Linux with KDE Plasma. 

## PRE-REQUISITIES 
Any Logitech mouse with secondary buttons (buttons other than left and right click and scroll wheel) interacts with the system using Hexadecimal code, ie, each button has a hexadecimal number assigned to it and we have to find each button’s hexadecimal code. Download and install [xdotool](https://blog.hostonnet.com/installation-of-xdotool-on-linux) in your system. 

After successful installation of xdtool, run it through the terminal. A small window with a box will pop up. When you pass your mouse through the box, it auto-fills the terminal with the exact pixel coordinates on where the cursor is currently located. Position the cursor inside the box and press the all the buttons one by one. The terminal will be auto-filled with the button id of the button pressed. Mark all the ids of the buttons. It is also important to know the name of the mouse for identification. To find the name of the mouse (there is a name used differently by the system to identify different mice) use [Solaar](https://pwr-solaar.github.io/Solaar/) or even xdotool can help with that. 

After the installation of xdotool and tracking of button ids, install logiops from their [official github repo](https://github.com/PixlOne/logiops). Once it is officially downloaded, install and run it. The configuration file of the logid will be stored in /etc directory.

Xdotool is a software that translates all the keypress from keyboard into keypresses or clicks from the mouse. All the mouse clicks will be translated as keyboard shortcuts in the back end of the system. All the keys in the keyboard have has a an unique string name and it can be found in Linus Torvalds’ official GitHub repo. That is the used as the reference in this project

Logiops contains the unofficial userspace drivers for HID++ Logitech devices.

## STEPS TO FOLLOW
1) Make sure the directory has the file logid.cfg . This is the configuration file of logiops. 
2) Make sure you are connected to the mouse through its USB receiver during this process
3) Make sure there are no background tasks running during the writing of this update
4) Make sure that the system is up to date and the kernel is updated to the it’s latest version available 
5)I would recommend using nano or vim as the text editor for this
6) After successfully copying the configuration file restart logid with systemctl restart command
7) Enable the logid to start while booting using “sudo systemctl enable —now logid”

**NOTE:** **Every time you update the configuration file don’t forget to restart logid immediately for the changes to be applied**
## MX Master owners

I tested this configuration file using Logitech MX Master 3. Here are the detailed explanations of what were the shortcuts that I had programmed

1) The thumb scroll wheel increases and decreases the volume. Scrolling left decreases the volume and scrolling right increases the volume
2) When the gesture button is pressed and pushed up, all the opened apps can be seen (Ctrl +F10)
3) When the gesture button is pressed and pushed down, it shows the desktop (Ctrl+F12)
4) When the gesture button is pressed and moved to the left, then it visits the tabs in the left of the current tab in the browser (Ctrl + Shift + Tab / Ctrl + Page Up)
5) When the gesture button is pressed and moved to the right, then it visits the tabs in the right of the current tab in the browser (Ctrl + Tab / Ctrl + Page Down)
6) When the gesture button is pressed normally, then it creates new tab in any app that has multiple tab functionality (including Dolphin) (Ctrl + T)’
7) The middle button, present under the scroll wheel, closes all the tabs (Ctrl + W)
8) Pressing the scroll wheel copies the content present and when clicked again it pastes the most recently copied content

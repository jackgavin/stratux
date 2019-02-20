How to compile and build Stratux executable

cyoung edited this page on Sep 24, 2018 · 3 revisions
Software can be compiled, linked and built on the Pi itself, probably the easiest and most compatible approach. Executable image files can then be run on any other supported model of the Pi (0, 2 or 3). The faster speed of the Raspberry Pi 3 compiles the code about 3x faster than a Pi2, and takes a few minutes.

Command line can be accessed either directly on the Pi itself (plug in HDMI monitor and USB keyboard) or remotely using a terminal window (Mac Utilities Terminal or Windows PC using PuTTY). The remote computer can be connected over Wi-Fi or Wired Ethernet using SSH.

From a remote computer (can be over Wi-Fi or wired Ethernet), login using SSH by opening a Terminal window in Mac or using PuTTY in Windows

ssh pi@192.168.1.76
_[password]_ raspberry
Or directly on the machine, login with username pi password raspberry

sudo su -
cd /root/
wget https://dl.google.com/go/go1.10.4.linux-armv6l.tar.gz
tar -zxvf go1.10.4.linux-armv6l.tar.gz
git clone --recursive https://github.com/jackgavin/stratux
cd stratux
service stratux stop
make
make install
service stratux start
Explanation
sudo enables supervisor privileges
stopping the stratux service releases the executable files in use and also frees up processing capacity
make invokes the Unix make process with the configuration file Makefile in the stratux directory
make install makes that target, creating a new image file
starting the stratux service runs the program again

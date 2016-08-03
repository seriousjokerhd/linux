# Fixes

* Terminal(Ubuntu) Shortcuts Ctrl + shift + V for paste. You can also change to CTRL+ V by going to shortcuts.

* Restart Network Manager from Terminal service network-manager restart

* Setting Global variables: (For applications to locate programs .. like anaconda pylint for sublime text) **add your path to source '/etc/environment'**

* AutoMount drives command: **_udisksctl mount -b /dev/sda2_**


* For Video tearing Install Latest **NVIDIA.run** OR download compizconfig-settings-manager from Software Center ..open CompizConfig and goto General   -> General Option -> Display Setting ... Uncheck detect Refresh rate put refresh rate 60 

* Getting Elementary OS interface back if changes Automatically... **_sudo apt-get install elementary-desktop_**

* Opening Terminal as root .... in Terminal >> **_sudo su_**  OR right click on terminal icon and select new windows as root OR search for root termnial in applications

* Opening Directory/Folder as root: **_gksu nautilus in terminal_**


### For low res splash screen after nvidia driver installation ...
1. sudo nano /etc/default/grub
> #GRUB_GFXMODE=1360x768x32
2. add the following line and leave above line commented out
> GRUB_GFXPAYLOAD_LINUX=1360x768x32
3. then 
sudo update-grub


### Install Elementary Tweaks 
1. sudo apt-add-repository ppa:versable/elementary-update

2. sudo apt-get update

3. sudo apt-get install elementary-tweaks

## Things to do after installing Linux

* Install Monaco font from Ubuntu Backup foler


# Installing NVIDIA
1. Copy NVIDIA.run from BackUp Ubuntu to Downloads
2. cd /home/rahul/Downloads
3. chmod +x NVIDIA.run
4. Ctrl + ALT + F2 ... Login 
5. sudo service lightdm stop OR sudo lightdm stop
6. cd /home/rahul/Downloads
7. sudo ./NVIDIA-.run
8. Restart Computer then  In terminal for nvidia settings  "nvidia-settings" 



# Android Development Environment

## Intsall JAVA JDK.
1. Copy "jdk-8u31-linux-x64.tar.gz" from Ubuntu Backup to Download directoy of New linux OS

2. Copy Java binaries into the /usr/local/java directory

3. cd /home/rahul/Downloads/
sudo cp -r jdk-8u31-linux-x64.tar.gz /usr/local/java/
cd /usr/local/java

4. Unpack the compressed Java binaries

5. sudo tar xvzf jdk-8u31-linux-x64.tar.gz

6. Double-check your directories.
>command: **_ls -a_**   
>> We should get... the following
>>> jdk1.8.0_20 
&   jre1.8.0_20

* Edit the system PATH file /etc/profile and add the following system variables to your system path. 

7. Command: sudo nano /etc/profile

8. Scroll down to the end of the file using your arrow keys and add the following lines below to the end of your /etc/profile file:

>JAVA_HOME=/usr/local/java/jdk1.8.0_31
PATH=$PATH:$HOME/bin:$JAVA_HOME/bin
export JAVA_HOME
export PATH

9. Ctrl + X to exit

* Inform your Ubuntu Linux system where your Oracle Java JDK/JRE is located. This will tell the system that the new Oracle Java version is available for use.

10. Command: sudo update-alternatives --install "/usr/bin/java" "java" "/usr/local/java/jdk1.8.0_31/bin/java" 1
this command notifies the system that Oracle Java JRE is available for use

11. Command: sudo update-alternatives --install "/usr/bin/javac" "javac" "/usr/local/java/jdk1.8.0_31/bin/javac" 1
this command notifies the system that Oracle Java JDK is available for use

12. Command: sudo update-alternatives --install "/usr/bin/javaws" "javaws" "/usr/local/java/jdk1.8.0_31/bin/javaws" 1
this command notifies the system that Oracle Java Web start is available for use

* Inform your Ubuntu Linux system that Oracle Java JDK/JRE must be the default Java.

13. Command: sudo update-alternatives --set java /usr/local/java/jdk1.8.0_31/bin/java
this command will set the java runtime environment for the system

14. Command: sudo update-alternatives --set javac /usr/local/java/jdk1.8.0_31/bin/javac
this command will set the javac compiler for the system

15. Command: sudo update-alternatives --set javaws /usr/local/java/jdk1.8.0_31/bin/javaws
this command will set Java Web start for the system

* Reload your system wide PATH /etc/profile by typing the following command:

16. Command: source /etc/profile
>Note your system-wide PATH /etc/profile file will reload after reboot of your Ubuntu Linux system

* A successful installation of Oracle Java 64-bit will display:
java -version
javac -version

17. Restart Computer



## Install Android Studio

1. Goto http://developer.android.com/sdk/index.htm  and download latest Android Studio for linux

* To set up Android Studio on Linux:

2. Unzip the downloaded ZIP file into "/Home" directory

3. To launch Android Studio, command:  **_android-studio/bin/studio.sh_**

4. Add Android Studio to Applications by going to Applications -> Main Menu ... We can add to command "android-studio/bin/studio.sh" and Icon 

5. You may want to add android-studio/bin/ to your PATH environmental variable so that you can start Android Studio from any directory.

6. If the SDK is not already installed, Copy the SDK folder in Ubuntu Backup and paste in android studio directory "Don't need to install 21 API platform already installed.

7. If you get build problem try.... sudo apt-get install gtk2-engines-murrine:i386

* Note: You may also need to install the ia32-libs, lib32ncurses5-dev, and lib32stc++6 packages. These packages are required to support 32-bit apps on a 64-bit machine.



### Install Genymotion ...rahulsenna 8758331775

1. copy the genytmotion.bin file from Backup Ubuntu to /Home directory of linux

2. cd /home/rahul/ OR don't do it because it's home directory

3. chmod +x genymotion.bin

4. ./genymotion.bin

5. Copy the "genymotion_vbox86p_5.0_141215_235800.ova" file from Backup Ubuntu and paste to .Genymobile -> Genymotion -> ova

6. Start genymotion by Clicking on "genymotion" executable or run ./genymotion

7. Choose Android 5.0.0 and Google Nexus 5 ... It won't download anything it will just deploy the "Virtual Device"

8. Android Studio -> Settings -> Plugins -> Browse Repositories .. Search for genymotion and install the plugin

9. Install Virtual box command: **_sudo apt-get install virtualbox_**

### IF PHONE DOESN'T SHOW UP BECAUSE OF PERMISIONS

* Create a file named /tmp/android.rules with the following contents (hex vendor numbers were taken from the vendor list page):

SUBSYSTEM=="usb", ATTRS{idVendor}=="0bb4", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="0e79", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="0502", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="0b05", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="413c", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="0489", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="091e", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="18d1", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="0bb4", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="12d1", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="24e3", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="2116", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="0482", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="17ef", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="1004", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="22b8", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="0409", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="2080", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="0955", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="2257", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="10a9", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="1d4d", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="0471", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="04da", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="05c6", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="1f53", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="04e8", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="04dd", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="0fce", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="0930", MODE="0666"
SUBSYSTEM=="usb", ATTRS{idVendor}=="19d2", MODE="0666"

* Run the following commands:

1. sudo cp /tmp/android.rules /etc/udev/rules.d/51-android.rules
2. sudo chmod 644   /etc/udev/rules.d/51-android.rules
3. sudo chown root. /etc/udev/rules.d/51-android.rules
4. sudo service udev restart
5. sudo killall adb
6. Disconnect the USB cable between the phone and the computer.


# Installing PHP

## Install Apache
1. sudo apt-get update
2. sudo apt-get install apache2
3. Open webbrowser and type localhost ... If everthing goes OK it will say "It Works".

## Install PHP
1. sudo apt-get install php5 libapache2-mod-php5 php5-mcrypt     "PHP home directory is "/var/www" need root permision to write or read use "gksu nautilus -in terminal" to change permision"
2. Search for PHP Modules apt-cache search php5-
3. Install Module/Library sudo apt-get install name of the module    



## Install MySQL
1. sudo apt-get install mysql-server libapache2-mod-auth-mysql php5-mysql
2. Once you have installed MySQL, we should activate it with this command:
3. sudo mysql_install_db
4. Finish up by running the MySQL set up script:
 sudo /usr/bin/mysql_secure_installation
5. The prompt will ask you for your current root password.
Type it in.

Enter current password for root (enter for none): 

OK, successfully used password, moving on...

Then the prompt will ask you if you want to change the root password. Go ahead and choose N and move on to the next steps.

Then Yes for all ..type Y 





# Hacking

## Installing reaver 

1. sudo su
2. sudo apt-get install libpcap-dev sqlite3 libsqlite3-dev libpcap0.8-dev

3. move to reaver archive directory e.g. **_cd /home/rahul/Hacking/_**

4. tar -xzvf reaver-1.4.tar.gz

5. cd reaver-1.4"

6. cd src

7. ./configure

8. make

9. sudo make install



## Installing AirCrack Suit

1. sudo su

2. sudo apt-get install build-essential

3. move to reaver archive directory e.g. cd /home/rahul/Hacking/
4. tar -zxvf aircrack-ng-1.2-rc1.tar.gz
5. cd aircrack-ng-1.2-rc1

6. sudo apt-get install libnl-dev

7. make
8. make install
9. airodump-ng-oui-update

## Hydra 

### How to work with Hydra

hydra smtp.live.com smtp -l rahulsenna@live.com -P /home/rahul/Desktop/pass.txt -s 587  -v -V

add -S for SSL

Kali-ARM-Build-Scripts
======================

Offensive Security Kali Linux ARM build scripts. We use these to build our official Kali Linux ARM images, 
as can be found at http://www.kali.org/downloads/

- These scripts have been tested on a Kali Linux 32 and 64 bit installations only, after making sure
that all the dependencies have been installed.
- Make sure you run the build-deps.sh script first, which installs all required dependencies.

- You will need to use the cross compilers from our github account.  

armel images (RPi) will use https://github.com/offensive-security/gcc-arm-eabi-linaro-4.6.2

armhf images will use https://github.com/offensive-security/gcc-arm-linux-gnueabihf-4.7

A sample workflow would look similar to (armhf):


    mkdir ~/arm-stuff
    cd ~/arm-stuff
    git clone https://github.com/offensive-security/gcc-arm-linux-gnueabihf-4.7
    export PATH=${PATH}:/root/arm-stuff/gcc-arm-linux-gnueabihf-4.7/bin
    git clone https://github.com/kwakwa/kali-arm-build-scripts
    cd ~/arm-stuff/kali-arm-build-scripts
    ./build-deps.sh
    ./olimex_lime2.sh 1.0


If you are on 32bit, after the script finishes running, you will have an image
file located in ~/arm-stuff/kali-arm-build-scripts/chromebook-1.0/ called
kali-1.0-chromebook.img and a sha1sum file for it.  **_You will need to use your own
preferred compression if you want to distribute it._**

On 64bit systems, after the script finishes running, you will have 3 files
located in ~/arm-stuff/kali-arm-build-scripts/chromebook-1.0; the sha1sum for
the uncompressed image file, the image file compressed via xz, and the sha1sum
file for the compressed image file.

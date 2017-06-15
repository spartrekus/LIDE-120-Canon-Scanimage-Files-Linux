# LIDE-120-Canon-Scanimage-Files-Linux
LIDE-120-Canon-Scanimage-Files-Linux


### WORKAROUND -  METHODE TO INSTALL LIDE 120 CANON (no warranty)

Info: no warranty. this method is by --forcing the installation. 
May break your system, but it works on my system ;)

PARKING IS NOT WORKING !!! IT CAN DAMAGE YOUR SCANNER !!!

1)
deb http://ftp.de.debian.org/debian testing main
deb-src http://ftp.de.debian.org/debian testing main


2) Important to remove xsane and the previous libsane 
apt-get remove --purge libsane*

3)  DETECTION.zip
    bring the correct *so* files for detecting the sanner, and 
    unpack it
    cp -a * /usr/lib/i386-linux-gnu/

4) unpacking the libsane backend !! It contains too scanimage !!
    herewith the tar.gz with the 1.0.27 source code

5) Compilation 

apt-get install libjpeg-dev
./configure 
make 
make install

go to sane-backends-1.0.27 

and type # scanimage -V  to see the scanimage version
then  type # scanimage -L  to see if you scanner is detected.

6) Parking !! set to 0, 0, position!!
   cd VueScan  and  ./vuescan 
   from vuex3295.tgz

7) Scan
 scanimage   --mode color  -t 0 -l 0 -x 210 -y 250  > test.pnm


8) Parking !! set to 0, 0, position!!
   cd VueScan  and  ./vuescan 
   from vuex3295.tgz

THIS METHOD IS A WORK AROUND And Has NO WARRANTY.

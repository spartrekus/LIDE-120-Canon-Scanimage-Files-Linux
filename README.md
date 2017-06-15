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



uname  -a...
4.5.5 #1 SMP   UTC 2016 i686 GNU/Linux

some modules present...
ahci                   36864  0
libahci                28672  1 ahci
xhci_pci               16384  0
libata                184320  2 ahci,libahci
xhci_hcd              151552  1 xhci_pci
usbcore               180224  9 uas,ath3k,btusb,uvcvideo,rtsx_usb,usb_storage,usbhid,xhci_hcd,xhci_pci
scsi_mod              180224  5 sg,uas,usb_storage,libata,sd_mod
usb_common             16384  1 usbcore
fan                    16384  0
thermal                20480  0
i2c_hid                20480  0
hid                    90112  4 i2c_hid,hid_multitouch,hid_generic,usbhid
sdhci_acpi             16384  0
sdhci                  40960  1 sdhci_acpi
mmc_core              106496  3 sdhci,sdhci_acpi,rtsx_usb_sdmmc


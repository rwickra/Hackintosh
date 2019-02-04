# Successful Hackintosh Project
#Hackintosh

I wanted to document in detail my process for getting a fully functional Hackintosh. I am using an older motherboard, but even with a massive amount of information out there about this build, it still took a substantial effort to get this done and tweak all the settings.  I spent about 2 weeks reading up about the project, putting together the build, and then troubleshooting the OS. My objective was to get this installation done completely using the “Vanilla” method, using only Clover Installer (CI) and Clover Configurator (CC).

Later, I intend to overclock the processor but what is displayed here is pre-Overclocking. So obviously some of the BIOS settings would change after OC is initiated.

_**My System Components**_

1. Intel i7-8700k Coffee Lake 3.6 GHz CPU
2. Gigabyte Z390 Aorus Master Motherboard
3. NZXT Kraken x62 AIO Cooler
4. 64 GB Vengeance LPX 3200 MHz DDR4 RAM
5. Samsung 970 EVO NVMe PCIe m.2 SSD 1 TB
6. AMD Radeon Vega 64 Frontier Edition (16 GB HBM2)
7. NZXT h500i Case
8. Fenvi FV-T919 Bluetooth/WiFi PCIe card (This has the Broadcomm chipset that normal Macs use) — cost me $55 on Newegg. 

## Online Guides I Used
* _r_Hackintosh Vanilla Guide [Getting Started - /r/Hackintosh Vanilla Desktop Guide](https://hackintosh.gitbook.io/-r-hackintosh-vanilla-desktop-guide/)
* u/cmer [GitHub - cmer/gigabyte-z390-aorus-master-hackintosh: A guide to build your own Hackintosh based on Gigabyte Z390 Aorus Master](https://github.com/cmer/gigabyte-z390-aorus-master-hackintosh)
* Gigabyte Z370 Gaming 5, 4K RX 580 - 10.13.4 SSDT [SUCCESS Gigabyte Z370 Gaming 5 - 4k RX 580 - 10.13.4 - SSDT | tonymacx86.com](https://www.tonymacx86.com/threads/success-gigabyte-z370-gaming-5-4k-rx-580-10-13-4-ssdt.250028/)
* Morganaut’s Build a Perfect Hackintosh [Build a Perfect Hackintosh - Beginners Tutorial - YouTube](https://www.youtube.com/watch?v=fA9AotXqkqA&t=781s) — An excellent starting point, but I used this only as a springboard and ended up changing much of the content. This tutorial, while great because of its simplicity, does not enable a lot of features you can get working with a little bit of tweaking.
* Carl Mercier’s Tutorial on Using Corpnewts USBMap Script. [How to fix USB 3 ports on a Hackintosh by generating your own SSDT or USBMap.kext - YouTube](https://www.youtube.com/watch?v=j3V7szXZZTc&t=83s) — This was the easiest method to create a custom SSDT to enable USB ports, but I ended up taking the hard route… well, just because I liked to challenge myself. The hard route is to do it manually using the instructions on the guide put together by Rehabman (listed below under “reading material”)
* Ibrahim Muslim’s Youtube Guide on SSDT Patching [USB 3.0 & 3.1 Permanent FIX | SSDT Patch | PART 1 of 3| For All MacOS X | 10.14.1 USB fix - YouTube](https://www.youtube.com/watch?v=dFihvGaLmMQ&t=10s) — I found this, a series of 3 Youtube videos, each running about 10 minutes to be rather long-winded but it gets the job done. Ultimately, after watching this video a few times, and re-reading Rehabman’s article (look under A Guide to Creating a Custom SSD for USBInjectAll.kext), I was able to do it successfully. 

## Reading Material
I read the following articles to inform me about exactly what was happening under the hood.
* Config.plist Wiki [Configuration](https://clover-wiki.zetam.org/Configuration#Config.plist-structure)
* Corpnewts USBMap Script [GitHub - corpnewt/USBMap: Py script for mapping out USB ports and creating a custom SSDT or injector kext (WIP).](https://github.com/corpnewt/USBMap) (I did not end up using this script although this makes the process insanely easy to generate your custom USB SSDT to enable USB ports. More later).
* The portion on the Coffee Lake Processor and the components of this config.plist in this guide was priceless. [Coffee Lake - /r/Hackintosh Vanilla Desktop Guide](https://hackintosh.gitbook.io/-r-hackintosh-vanilla-desktop-guide/config.plist-per-hardware/coffee-lake)
* An Idiots Guide to Lilu and its Plugins [An iDiot’s Guide To Lilu and its Plug-ins | tonymacx86.com](https://www.tonymacx86.com/threads/an-idiots-guide-to-lilu-and-its-plug-ins.260063/)
* A Guide to 10.11 USB Changes and Solutions by Rehabman [Guide 10.11+ USB changes and solutions | tonymacx86.com](https://www.tonymacx86.com/threads/guide-10-11-usb-changes-and-solutions.173616/) — Very important to understand how MacOS has changed how it accesses USB. An important primer to understand the next article which is quite complex.
* A Guide to Creating a Custom SSDT for USBInjectAll.kext [Guide Creating a Custom SSDT for USBInjectAll.kext | tonymacx86.com](https://www.tonymacx86.com/threads/guide-creating-a-custom-ssdt-for-usbinjectall-kext.211311/)


## Download Resources
* Clover Installer ([Clover EFI bootloader -  Browse /Installer at SourceForge.net](https://sourceforge.net/projects/cloverefiboot/files/Installer/)
* Clover Configurator  [Download Clover Configurator 5.4.0.0 | mackie100 projects](https://mackie100projects.altervista.org/download-clover-configurator/)
* GoldFish64’s Kext Repo [OneDrive](https://onedrive.live.com/?authkey=%21APjCyRpzoAKp4xs&id=FE4038DA929BFB23%21455036&cid=FE4038DA929BFB23) — This has a wonderful repo of always updated, newest kext versions.
* OsxAptioFix2Drv-Free2000.efi  [EFI-X99/OsxAptioFix2Drv-free2000.efi at master · koush/EFI-X99 · GitHub](https://github.com/koush/EFI-X99/blob/master/CLOVER/drivers64UEFI/OsxAptioFix2Drv-free2000.efi)  — seems to be a very useful driver, but I did not use it for my motherboard. I’m putting it here since I experimented with it, and it is not available in most repos. 
* VegaTab-En — Vega 64 Kext Creator - [VGTab-en.zip - Google Drive](https://drive.google.com/open?id=1BHmkaoCzXD6xAq_-iKrhPM0z2eQhaitI) 

## Purpose of Hackintosh
1. Give myself a challenge, to see if I could still do it. My Mac is about 7 years old now.
2. 4K Video Editing without lag.

## What Works
1. Ethernet
2. Audio
3. APFS
4. Sleep/Wake
5. Headless iGPU with Native Support for Quicklook, Preview, JPG, Final Cut Pro X
6. All USB ports functioning at USB 3 speeds
7. iServices (iMessage, Appstore, Facetime, Handoff, Continuity)
8. WiFi
9. Bluetooth (via Broadcomm PCIe card)
10. Unlock and Apple Watch
11. Air Drop
12. Apple Music
13. Power Nap

# What Doesn’t Work
1. USB-c ports — They function at USB 3.0 speeds.
2. iGPU HDMI or DVI output during installation. Seems to be a common issue and it doesn’t matter to me since I installed via Vega Card.
3. Built-in WiFi — Didn’t work (MacOS didn’t even recognize that the system had WiFi).
4. Onboard Bluetooth — Recognized by MacOS, but was acting weird and not connecting to devices, until I permanently disabled the controller and enabled the USB driver Bluetooth from my PCIe card.
5. Netflix DRM in Safari - For some bizarre reason it works on Chrome. 

## Haven’t Tested
1. Thunderbolt 3 - The header is present on this motherboard, and I have to purchase a Titan Ridge Card to test it out. People say it works, so I will report back when I test it out.
2. FileVault — I did not install some of the initial drivers required for this.

## BIOS Settings (Gigabyte BIOS F11)
**Note:** I initially updated the BIOS to version F12c which is the latest from the version that was available when I got my motherboard F6. This created some problems where the system would hang during very first boot up of MacOS (see #1 under issues and lessons).

*  Load Optimized Defaults
* M.I.T. (You can ignore the M.I.T. settings if you don’t have the same memory frequency I have. I did this because I wanted to be able to enable XMP but this created a problem during boot up where the USB drives would get ejected when recovering from sleep-wake. The solution to this was to enable XMP but dial down the memory frequency to 2666 MHz as I have done below. However, this part is unnecessary if you don’t care about getting the best performance out of your memory). 
	* -> Memory Frequency Settings 
		* -> Extreme Memory Profile (X.M.P.) -> Profile1
		* -> System Memory Multiplier -> 26.66        32.00
		* -> Memory Ref Clock -> Auto
		* -> Memory Odd Ratio -> Auto
		* -> Memory Boot Mode -> Normal
		* -> Memory Frequency -> 2666 MHz            3200 MHz
* BIOS
	* -> Security Options -> System
	* -> Boot Option Priorities -> UEFI OS (Samsung)
	* -> Fast Boot -> Disabled
	* -> Windows 8/10 Features -> Windows 8/10
	* -> CSM Support -> Enabled
	* -> LAN PXE Boot Option ROM -> Disabled
	* -> Storage Boot Option Control -> UEFI
	* -> Other PCI Devices -> UEFI
* Peripherals
	* -> Initial Display Output -> PCIe 1 Slot
	* -> Above 4G Decoding -> Disabled (I enabled this and system crashed)
	* -> LEDs in Sleep, Hibernation or Soft Off State -> Disabled
	* -> Intel Platform Trust Technology -> Disabled
	* -> SW Guard Extensions (SGX) -> Disabled
	* -> USB 3.0 DAC-UP 2 -> Normal
	* -> Trusted Computing -> Disabled
	* -> Intel BIOS Guard Technology -> Disabled
	* -> USB Configuration 
		* -> XHCI Hand Off -> ENABLED
	* -> Network Stack Configuration 
		* -> Network Stack -> Disabled
	* SATA and RST Configurations
		* -> SATA controllers -> Enabled
		* -> SATA Mode Selection -> AHCI
* Chipset
	* -> VT-d -> Disabled
	* -> Internal Graphics -> Enabled
	* -> DVMT Pre-Allocated -> 128M
	* -> DVMT Total Gfx Mem -> 256M
	* -> Audio Controller -> Enabled
	* -> PCH LAN controller -> Enabled
	* -> Wake on LAN -> Disabled
	* -> IOAPIC 24-119 -> Enabled
* Power
	* -> Platform Power Management -> Disabled
	* -> AC Back -> Always On
	* -> ErP -> Disabled



# Creating USB Installer
* For ease of use, I used a 32 GB USB Drive and downloaded the “Install MacOS Mojave.app” installer.
* I formatted the USB drive using Disk Utility, being careful to ensure that the main drive is erased, with _GUID Partition Map_ and _MacOS Journaled Format_.
*  Then, run the following command to install Mojave.

```
sudo “/Applications/Install macOS Mojave.app/Contents/Resources/createinstallmedia” —volume /Volumes/USB
```

* This will take some time, without much output (even 30-40 minutes) but it will complete. 
* This process now put the MacOS installer into the USB drive, but the USB drive still is **not** bootable. To create this into a bootable drive, we have to utilize the Clover Installer/Builder and install an EFI partition.


# Download Clover Builder and Configurator
1. Gather the download apps including Clover Builder [Releases · Dids/clover-builder · GitHub](https://github.com/Dids/clover-builder/releases) and Clover Configurator [Clover Configurator (Global Edition) | mackie100 projects](https://mackie100projects.altervista.org/download/ccg/).
2. Clover Builder (CB) is for creation of the bootloader on the USB drive
3. Clover Configurator (CC) is to configure the mackintosh.
4. In the Vanilla method, the objective is to install all of the configuration for the entire MacOS inside the EFI partition in the bootable drive (whether this is the USB drive, or eventually the hard drive in which your OS resides). The major advantage of this system is that the physical OS can be recognized and function completely normally in any real Mac, because all the files that make it run in a PC environment are isolated in the EFI. I personally liked this method a lot because it is much easier to trouble shoot and in theory, unless the MacOS upgrades change their implementation of certain device drivers etc, the upgrade should not break your installation. But it does happen occasionally, but the fixes can be applied rather quickly.
5. I Installed Clover_v2.4k_r4866.pkg  — You may have downloaded a newer version. That is fine.
6. Run Clover Installer. Once you get to the destination select, **remember to choose the USB drive** and not the default hard drive/SSD. Then remember to hit **customize**. This will enable you to select the following option in your installation.
7. Chose **Clover for UEFI Booting Only**
![](Successful%20Hackintosh%20Project/Screen%20Shot%202019-01-28%20at%208.06.08%20PM.png)
3. Under **UEFI Drivers** chose the following options:
![](Successful%20Hackintosh%20Project/Screen%20Shot%202019-01-28%20at%208.07.15%20PM.png)
4. For Simplicity sake, to start off with, I will be only running 3 UEFI drivers:
	1. **APfsDriverLoader-64** :  This allows the boot loader (Clover) to see and boot from APFS volumes by loading APFS.efi. Usually in conjunction with AptioMemoryFix-64.
	2. **AptioMemoryFix-64** : This includes fixes for NVRAM and better memory management. This turns out to be a finicky beast. For my motherboard, I had no issues with this alone, but as I was tinkering with other boards, I found that this caused problems. There are several other alternate drivers including OsxAptioFixDrv.efi, OsxAptioFixDrv2.efi, OsxAptioFixDrv3.efi — these are not newer versions of the other, but rather three separate variants. If AptioMemoryFix-64 gives you trouble, try one of these. 
	3. **HFSPlus.efi** (or VBoxHfs-64.efi) : These are required for Clover to see and boot from HFS+ volumes.  If you can’t see HFSPlus, don’t worry about it. We can install it later. Alternatively, if you see VBoxHfs-64, it does the same thing.

The above files are the most critical. I added three more drivers to enable various functions. 
	5. **FSInject.efi** :  This was added automatically during installation so I never deleted it. It appears its function is to block files from being loaded and to inject files from pre-exit boot services for the kernel.
	6. **NTFS-64.efi** : This enables the boot loader to see NTFS.
	7. **VirtualSMC-64.efi** : 

5. Now we have to gather up our KEXT files (Kernal Extensions). Kext files are basically the drivers for macOS. The word “Kext” is short for Kernel Extension. Kexts are an extension of the macOS kernel. When you boot up your machine the code contained in these kexts is atomically injected into the operating system. It’s like having drivers contained in a single file without having to install them like on Windows. When you want to uninstall a kext all you have to do is remove it (Source: [What are kext files in macOS? - Hackintosher](https://hackintosher.com/blog/kext-files-macos/)) 
6. A key thing to remember here is that normal Macs also use Kexts, and these are saved in _System_Library_Extensions_ by default.  For this reason, I prefer to save my _modified_ kexts elsewhere, so that there is no confusion about which ones come with the OS and which ones are introduced by a hackintosher. In the vanilla method, all of your kexts are stored in _EFI_clover_kexts_ folder, completely separate from the rest of the OS.
7. We are going to begin by gathering kexts for the Hackintosh. I’m only going to start with the bare essentials, because of the purpose is the keep the system running as close to a real Mac and lean as possible. 
8. Clover Configurator (CC) has a Kext installer, but I prefer to do it manually. 

## Gathering Kexts
Most of the Kexts are available from the following repos:
	Goldfish64 Repo : [Microsoft OneDrive - Access files anywhere. Create docs with free Office Online.](https://1drv.ms/f/s!AiP7m5LaOED-m-J8-MLJGnOgAqnjGw)
Once the following kexts have been downloaded and unzipped, I copy them directly into the _EFI_Clover_Kexts_Other/ folder within the EFI partition of the boot loader drive that was prepared by Clover Builder.

### SMC
_VirtualSMC.kext_ - Emulates the SMC chip on real macs. There is an alternate version called _FakeSMC.kext_ which essentially does the same thing. FakeSMC is more tried and true, and VirtualSMC is the new kid in town. VirtualSMC also comes packaged with a UEFI driver. They both have hardware monitors that can be used to monitor CPU temperature, speed, GPU function etc. Install **either** VirtualSMC or FakeSMC, not both.

### Graphics
_WhateverGreen.kext_ 
_Lilu.kext_ 
Is a combined kext that incorporates the features a number of prior kexts that directly dealt with graphics from various cards and chipsets. They have now been combined to this one kext, along with its’ companion kext _Lilu.kext_.

### Ethernet
 _IntelMausiEthernet.kext_ - this works with most newer Intel LAN chipsets. This should work in the chipset for **Intel GbE LAN** which in in my motherboard.

### Audio
_AppleALC.kext_  : This motherboard has the **Realtek ALC1220** Codec, which is supported by the _AppleALC.kext_. 

### WiFi and Bluetooth
Apple does not recognize the Intel WiFi chip so I am using a BCM93460 FenVi FV-T919 wifi/bluetooth card which should be supported directly out of the box.

### USB
_USBInjectAll.kext_ - is required. You’ll want to grab  [USBInjectAll.kext](https://bitbucket.org/RehabMan/os-x-usb-inject-all/downloads/) . If you’re on an H370, B360, and H310 Coffee Lake system, or an X79/X99/X299 you’ll likely want to make sure to include the _XHCI-unsupported.kext_ as well. As of 10.11, Apple has imposed a 15 port limit on each USB controller. This doesn’t sound like a terribly imposing issue until you realize that each USB 3 port counts as 2 - one for USB 2, one for USB 3. On Skylake and Coffeelake builds where USB 2 and 3 are handled only on XHCI, and each USB 3 port counts as 2, this limit can be reached quickly. This was one of my issues with my board. There is a way to route all USB 2 through EHCI though - utilizing RehabMan’s  [FakePCIID.kext + FakePCIID_XHCIMux.kext](https://github.com/RehabMan/OS-X-Fake-PCI-ID)  (it only works on some chipsets though, and not mine, unfortunately) which can take some of the pressure off the XHCI controller. (Source : [Gathering Kexts - /r/Hackintosh Vanilla Desktop Guide](https://hackintosh.gitbook.io/-r-hackintosh-vanilla-desktop-guide/gathering-kexts)).  For example, it appears that while the Z370 chipset does not have EHCI controller (and all of the USBs are routed via XHCI), some of the Z390 motherboard chipsets do have the ability handle routing via EHCI.

Handling USB issues ended up being one of my biggest problems but it was resolved, thanks to the hard work of some wonderful folks who had created some amazing tools (CorpNewt, Rehabman) . See my troubleshooting section.

So my final kext collection copied into the _EFI_Clover_Kexts_Other was as follows. You will note that there are multiple 10.xx folders in the kexts folder and a single “Other” folder. I deleted all of the other 10.xx folders since they are version specific, and the “Other” folder is universally accessed. Which is what I want.


	1. AppleALC.kext 
	2. IntelMausiEthernet.kext
	3. Lilu.kext
	4. WhateverGreen.kext
	5. VirtualSMC.kext
	6. SMCBatteryManager.kext
	7. SMCLightSensor.kext
	8. SMCProcessor.kext
	9. SMCSuperIO.kext
	10. USBInjectAll.kext
	11. XHCI-unsupported.kext
	12. GenericUSBXHCI.kext — I’m not sure whether this is redundant, but I read that this can enable injection of non-Intel USB ports. I have 2 USBc ports that are regulated via the ASMedia controller, so I activated them anyways. However it doesn’t appear to have worked. So you perhaps don’t need this.

# Changing Config.Plist
The config.plist is the main configuration file for the Hackintosh. In order to minimize the effects of it, I am going to delete the existing one on the EFI partition and import a new config.plist from a source.

1. Open the following website : [Coffee Lake - /r/Hackintosh Vanilla Desktop Guide](https://hackintosh.gitbook.io/-r-hackintosh-vanilla-desktop-guide/config.plist-per-hardware/coffee-lake) — This is the Coffee Lake Config.plist guide. Read this article carefully as it documents what you need to know about each of the parameters. This is a .plist file that contains instructions for the boot loader. It can be edited either by directly modifying the code or by loading into an editor such as Clover Configurator. 
2. Go to the bottom of the webpage and click this link (sample config.plist ) : [Hackintosh-Guide/config.plist at master · corpnewt/Hackintosh-Guide · GitHub](https://github.com/corpnewt/Hackintosh-Guide/blob/master/Configs/CoffeeLake/config.plist)
3. This will connect you to a GitHub site. Select [Raw]
4. When a new page loads, Select All [CMD-A] and Copy the content [CMD-C].
5. Now open up TextEdit or TextWrangler.
6. If using TextEdit, go to Format -> Make Plain Text
7. Paste the text in there and save the file as **config.plist** to the desktop.
8. Now ensure that the newly formatted and prepared USB drive (with Clover Installer) is ready. This USB drive should have the UEFI drivers installed in the _EFI_Clover_Drivers64UEFI_ and the kexts installed in _EFI_Clover_kexts_other/. 
9. Now startup Clover Configurator and choose Mount EFI -> EFI partition of USB drive -> Mount Partition (if this hasn’t been done already).
10. Navigate to _EFI_Clover_config.plist_ and delete the existing file on the USB drive. This file was automatically created by the Clover Installer and **not** what we want. Copy the **config.plist** that you created by cutting and pasting text from the website above from Corpnewt to the location _EFI_CLOVER/config.plist.
11. Right click on the config.plist and choose Open with -> Clover Configurator.


# Walkthrough of Clover Configurator
13. Let’s go through each of the screens to understand what’s going on. You don’t have to read through this, but I try my best to explain what I’ve learned about each of the settings in clover and what they mean. You don’t necessarily have to read it. You can certainly boot the computer without any of this.

## ACPI
![](Successful%20Hackintosh%20Project/3C8A0FD9-EEDD-4A71-AAB0-6FA2C44B1107.png)

*  The first screen shows ACPI configuration. This includes DSDT and SSDT patches. **ACPI**(Advanced Configuration and Power Interface) is an industry specification for the efficient handling of power consumption in desktop and mobile computers.**ACPI**specifies how a computer’s basic input/output system, operating system, and peripheral devices communicate with each other about power usage. It provides an open standard that operating systems can use to discover and configure computer hardware components, to perform to perform power management by (for example) putting unused components to sleep, and to perform status monitoring. The ACPI is specified by two types of tables.
	* DSDT : Differentiated System Description Table is used to describe what peripherals the machine has. Also holds information on PCI IRQ mappings and power management..
	* SSDT : Secondary System Description Table, which is like an extended version of DSDT.
* This distinction is important because we can set DSDT and SSDT patches to modify the ACPI when the Hackintosh is loading. Several above include:
	* Change XHCI to XHC
	* Change SATA0 to SATA
	* Change GFX0 to IGPU
	* Change HDAS to HDEF
* The SSDT table is seen on the bottom right — SSDT-UIAC.aml is a file we will create later to specify our USB devices.

## Boot
![](Successful%20Hackintosh%20Project/414635A6-1537-4FB1-BC81-0F75B07F3366.png)

* These set of options specify what happens when the system boots. Under arguments, you may want to check the following:
	* `Verbose (-v) `: Provides verbose mode.
	* `Slide=0` : unclear to me what this exactly does, but I found on several forums that the issue of USB drives getting ejected was avoided with this and setting darkwake=on. I did not have this issue.
	* `Dart=0` : An extra layer of protection against Vt-d issues
	* `Debug=0x100` : This prevents a reboot during a kernel panic. Helpful to see what happens that leads to the kernel panic.
	* `Keepsyms=1` : This is a companion setting to debug=0x100. Tells the OS to print the symbols during a kernel panic.
	* Under custom flags :
		* `shikigva=40`  : This is a flag specific to iGPU.
* `DefaultBootVolume` : This uses NVRAM to remember which volume was last booted by Clover and auto selects the same volume for booting.
* `TimeOut` : This is the number of seconds before the DefaultBootVolume auto boots. Setting this to -1 avoids all timeout, or to 0 to skip the GUI entirely. If set to 0, you can press any key at the boot to get to the GUI to show back up.
	
## Devices
![](Successful%20Hackintosh%20Project/E3A6AF02-408B-4C33-878A-C8A3E9622E0C.png)

* We are going to skip ahead to this section. This is a very important section also. Pay attention to the bottom right, and choose _properties_. This is where we will be changing some parameters associated with activating a headless iGPU.
* The primary purpose of this section is to handle property injection for the _WhateverGreen.kext_ here. Some key things to note here: 
* **USB**:  Under this section, we ensure that _Inject_ and _FixOwnership_ are selected to avoid issues with hanging at a half-printed line somewhere around the Enabling Legacy Matching verbose line. You can also get past that by enabling XHCI Hand Off in BIOS.  

* **Audio**:Here we set our audio to inject **Layout 11** - this may or may not be compatible with your codec, but you can check on AppleALC's Supported Codec Page. For me, both Layout 1 and Layout 11 gave good results.  We also **enabled ResetHDA** which puts the codec back in a neutral state between OS reboots. This prevents some issues with no audio after booting to another OS and then back.

* **Properties**:  This section is setup via Headkaze's Intel Framebuffer Patching Guide [Intel Framebuffer patching using WhateverGreen - Lilu and plugins - InsanelyMac Forum](https://www.insanelymac.com/forum/topic/334899-intel-framebuffer-patching-using-whatevergreen/?tab=comments#comment-2626271) and applies only one actual property to begin, which is the _ig-platform-id_. The way we get the proper value for this is to look at the _ig-platform-id_ we intend to use, then swap the pairs of hex bytes. To make matters simple, this is how it goes:

If you want the iGPU to drive a display : `07009B3E` 
If you want the iGPU to run headless (without display) used only for compute tasks : `0300923E` 

In order for FCPX to run efficiently, Intel QuickSync should be enabled, and this as well as other functions, rely on the iGPU to offload the main GPU. Thus, I chose to run my iGPU in headless mode by setting the parameter:

```
AAPL;ig-platform-id 	0300923E	DATA
Device-id				923E0000	DATA
```

We will discuss this more under (Enabling Headless iGPU) under troubleshooting section. 

We also add 2 more properties, _framebuffer-patch-enable_ and _framebuffer-stolenmem_. The first enables patching via WhateverGreen.kext, and the second sets the min stolen memory to 19MB.

## GUI
![](Successful%20Hackintosh%20Project/EB46ED4D-9657-431F-B999-3981E83816AC.png)

This section sets parameters for the Clover Boot Manager (CBM) GUI that shows up when you first enter. There is nothing major here to remember since a lot of what happens here is cosmetic.

**Scan**
The only settings I've tweaked on this page are the Scan settings. I've selected Custom, then checked everything except Legacy and Kernel. This just omits some of the unbootable entries in Clover to clean up the menu.

**Hide Volumes:**
I haven't added anything here, but you can hide unwanted volumes here. You can do so by either adding the volume's name, or UUID.
To hide extra APFS entries, add the following to this list:

`Preboot`
`Recovery`

To hide all Recovery partitions, add `Recovery` to the list.

Alternatively, you could also do the same by choosing custom entries. If you choose this option, you can specify which boot drives to show on clover at startup. Since I have a Windows 10 partition, for example, I can open up the options for this, as shown below. Under this, I  directly choose the UUID for the partition (NOTE: this is a partition UUID, not Volume UUID). 

![](Successful%20Hackintosh%20Project/5C688A0D-53C1-4DC3-A9F2-8D70E9C3D5BC.png)

To get the UUID of a drive to hide, you can use the following terminal command:

`Diskutil list`

`diskutil info diskXsY | grep -i "Partition UUID" | rev | cut -d' ' -f 1 | rev`

Make sure to replace diskXsY with the actual disk number of the volume you'd like to hide.

## Kernel and Kext Patches
![](Successful%20Hackintosh%20Project/A7DADF7C-6E32-45F9-B044-084EFB558109.png)

* This screen shows a series of kext patches that were applied. I believe a lot of these kext patches have to do with increasing the port limit during various iterations of MacOS 10.x.x so as far as I am concerned the one that matters is really the AppleAHCIPort. This last one acts as an orange icons fix - when internal drives are hotpluggable, and treated as external drives. I believe the others can be removed safely (although I did not). For more information on what this is accomplishing, see my troubleshooting section on Custom SSDT for USB 2.0 and 3.0.
* **Checkboxes:**
We have a couple checkboxes selected here:

`Apple RTC` - this ensures that we don't have a BIOS reset on reboot.
`KernelPM` - this setting prevents writing to MSR 0xe2 which can prevent a kernel panic at boot.

**Rt Variables**
![](Successful%20Hackintosh%20Project/27509F54-E5DF-4DED-9035-6F84444F06D2%20copy.png)

* The next three sections, **Rt Variables, SMBIOS, System Parameters**, have to do with setting up System Integrity Protection, iMessage and other iServices. I won’t get into the details of this here, so read up on the trouble shooting section about setting up SMBIOS and iServices.

## System Parameters 
![](Successful%20Hackintosh%20Project/CFA9CD75-CE69-4805-A614-B066A6203B44.png)
* The only real important thing here is to check the box that states “Inject kexts”. This essentially tells the system to inject any and all kexts to the loading MacOS.
* `InjectSystemID` : This is also checked. This tells Clover to set the SmUUID as the `System-ID` at boot. This is again reportedly important to get iServices working properly. 

## Clover Tools
There are several clover tools that we will be using regularly.

**Mount EFI**
![](Successful%20Hackintosh%20Project/753D8419-6950-4D50-A487-F42B8BA02C5D.png)

This screen helps mount any EFI partitions we need to make changes to the _EFI_Clover folder, for example.

**Install Drivers**
![](Successful%20Hackintosh%20Project/9A978C92-68AC-4FD5-9C5D-29B726D6BFE9.png)

This tool helps you install the latest version of any UEFI drivers. Note the green indicators under the **Drivers UEFI 64-Bit** section. The Drivers BIOS 64 Bit are for BIOS based motherboards, and these days virtually everything is UEFI based.

**Kexts Installer**
![](Successful%20Hackintosh%20Project/D0A78725-E26E-4FF6-A899-EC11D0548929.png)

This is an easy utility to install Kexts directly from Clover. A couple of things to remember:
	1. Always set the OS version (top right) to “Other”. To avoid conflict, I actually delete all the other OS folders in the _EFI_CLOVER_kexts_ folder so that the only one remaining is _EFI_CLOVER_kexts_other/.
	2. You can directly check the boxes and the latest kexts from a repository will be downloaded. Some kexts such as VirtualSMC can have additional power-monitoring kexts downloaded. These are deposited in the kexts folder in the EFI partition, and NOT in the system_library_extension/ which is where Apple usually places its kexts. 
	3. In lieu of using this Kext Installer, you could simply copy your latest kext files into the _EFI_Clover_kexts_other/ folder also. They both accomplish the same thing.

# First Boot
* Eject the drive that now contains MacOS Mojave installed, along with an active boot loader (via Clover installer) and a config.plist that we modified using Clover configurator.
* At the BIOS screen, choose boot drive and select the USB drive.
* **Boot from the USB drive** on Clover.
* Now you will probably see verbose text, and if everything goes right you will get to the screen that states “Please Choose your Language” 
* Incidentally, this is where I hit my first problem. Please see ( [System Hangs during First Boot even before the First Graphics Screen was visible](bear://x-callback-url/open-note?id=9A092091-9EE0-4071-BE1E-9CBE8613C432-520-00000387F13F3F7F) )  Under Troubleshooting.
* Once you have accepted the license agreement, and are greeted with the first menu, instead of choosing “Install MacOS”, instead choose “Start Disk Utility”.
* Under Disk Utility, select the drive that you plan to install MacOS into.
* Format this drive in APFS format.
* Now close Disk Utility and when you return to the Menu choose to “Install MacOS”.
* The installer will continue here, and should reboot at least twice. Don’t touch anything during this reboot, since Clover will automatically choose the “Preboot” volume, which is correct. 
* Let the installation complete.
* The next time the system reboots, choose “**Boot from MacOS SSD**” (or whichever drive you wanted MacOS installed into) from the boot menu.
* If everything goes well, you should boot into MacOS.

# Checking to Ensure Everything is Working
* First place to head over to is Apple Menu -> About this Mac -> System Report. 
* Make sure that an Audio Device, Ethernet, Bluetooth and WiFi are working. These are the usual culprits and in my case Audio and Ethernet was functional, but Bluetooth and WiFi was not.
* We will look at how to activate some of the other nonfunctioning systems out of the box, in the section on troubleshooting below.

# Transferring functioning EFI folder from USB boot loader to EFI partition on SSD.
* Assuming that everything is working, once everything is said and done, you should be ready to transfer the EFI partition from the USB drive to the SSD. This is because the SSD now has MacOS installed, but does not have a boot loader to inject the UEFI drivers and kexts during boot up. This information is in the EFI partition in the USB installer.
* So have to repeat the previous process. However, don’t format the SSD (It already now has MacOS installed). So what we need to do is just run Clover Installer/Builder to create the boot loader. 
* Run it as we have done before on the USB drive, but under destination, now choose the SSD. Select the same options as we had done before.
* The next part is a little bit different. You don’t need to download a config.plist or load clover. We’ve already painstakingly tweaked clover and config.plist along with the kexts that we need. All those tweaks are in the USB drive’s EFI partition.
* So, using Clover Configurator, what you need to do is mount the EFI partitions in the USB drive that you loaded MacOS from, and the SSD to which you installed MacOS. Delete the EFI folder in the EFI partition inside the SSD and copy the EFI folder from the EFI partition in the USB. This should create a copy of the boot loader into the SSD.
* Now reboot your system. Remove the USB drive.
* If everything went as planned, your system should boot from the SSD without the USB.



# TROUBLESHOOTING
## Settings Changes were NOT taking effect after reboot.
On several occasions I ran into this weird bug where I would either remove a SSDT or DSDT patch and/or make a change and reboot the system, but the system would behave as if I didn’t make the change. I could not figure out until I found some information that it helps to boot into windows. Bizarre, right?

When this didn’t happen, all I needed to do was to go into a Windows installation from Clover, play around a little bit, exit and reboot into MacOS and the problem was solved. 

## System Hangs during First Boot, even before the first graphics screen was visible. 
This is one of the first errors I encountered that frustrated the heck out of me.  I tweaked with a lot of memory drivers including deleting AptioMemoryFix.efi, adding OsxAptioFixDrv2, OsxAptioFixDrv3, EMUVariable64.efi etc, and nothing worked. Finally, it turned out I had upgraded my Gigabyte Motherboard BIOS to a version (F12c) that was causing this issue. I downgraded the BIOS to F11 and the system booted up immediately. 

## USB drives constantly get ejected during sleep and when computer wakes up drives have been improperly ejected
This was a much more interesting problem, and reportedly has to do with RAM management. I noticed that in the BIOS, if I turned off XMP (Extended Memory Profile) this problem went away. However, I did not want to do this since I fully intended to overclock my system. I then found a great post on TonyMacX86.com ([USB drives getting ejected when Hackintosh wakes from sleep with XMP enabled | Page 2 | tonymacx86.com](https://www.tonymacx86.com/threads/usb-drives-getting-ejected-when-hackintosh-wakes-from-sleep-with-xmp-enabled.251488/post-1865336)) which had the solution in this post that I linked. Basically, it turns out that the fastest Apple computers today (Jan 2019) the iMac Pro has only 2666 MHz DDR4 RAM, so you cannot go over that number in your base config. The solution was manually setting the RAM frequency down to 2666 MHz in the base config and then changing it up to 3200 MHz in the XMP and activating the XMP to Profile 1.  I am going to repost the relevant section from the BIOS that corresponds to this. 
- - - -
M.I.T. (You can ignore the M.I.T. settings if you don’t have the same memory frequency I have. I did this because I wanted to be able to enable XMP but this created a problem during boot up where the USB drives would get ejected when recovering from sleep-wake. The solution to this was to enable XMP but dial down the memory frequency to 2666 MHz as I have done below. However, this part is unnecessary if you don’t care about getting the best performance out of your memory). 
	* -> Memory Frequency Settings 
		* -> Extreme Memory Profile (X.M.P.) -> Profile1
		* -> System Memory Multiplier -> 26.66        32.00
		* -> Memory Ref Clock -> Auto
		* -> Memory Odd Ratio -> Auto
		* -> Memory Boot Mode -> Normal
		* -> Memory Frequency -> 2666 MHz            3200 MHz
- - - -

## Onboard WiFi was not detected, and Bluetooth was extremely buggy.
As it turns out my motherboard has an internal Wifi card based on Intel which is not supported by Apple. Apple’s WiFi is supported by Broadcom. As such, I was able to buy a WiFi card from Ebay/NewEgg for about $50. The card I bought is linked below. Fenvi FV T919. This is a WiFi and Bluetooth card (PCIe x1 based, but the Bluetooth works via a separate USB controller that is accessed via a motherboard USB header).

[Fenvi FV-T919 Wireless AC1300 PCI Express Wi-Fi Adapter, Support Hackintosh / Mac OS, Dual Band, Up to 1300Mbps Data Rates, IEEE 802.11ac/a/b/g/n, Bluetooth 4.0,  Broadcom BCM94360 Wifi Card - Newegg.com](https://www.newegg.com/Product/Product.aspx?Item=9SIADXZ7GS4848&ignorebbr=1&source=region&nm_mc=KNC-GoogleMKP-PC&cm_mmc=KNC-GoogleMKP-PC-_-pla-fenvi+Official+Store-_-Network+-+Wireless+Adapters-_-9SIADXZ7GS4848&gclid=CjwKCAiAv9riBRANEiwA9Dqv1bKTtaVntm__KfXzHxAmSRo3uErduX9C_JP5fwgfwDws1Bn3UUM0PhoCX8EQAvD_BwE&gclsrc=aw.ds)

The subsequent problem I ran into was with Bluetooth. The motherboard Bluetooth was recognized by MacOS alongside the BT from the Fenvi card, but when I try to connect there appeared to be some conflict rendering the overall BT nonfunctional. I fixed this during the time I applied the USB patch with an SSDT.  Please see that section for further information. But briefly, I ended up identifying that the internal BT controller works off of a USB controller (HS02) which I could shut off when I did the custom SSDT for USB ports. Once I shut off the USB controller for the internal BT, the Fenvi card’s bluetooth was the only thing that was active and it was fully operational.


## Audio not high quality.
Audio issues were really minor, but I did notice that the audio quality could be better. The fix for this was to apply a DSDT patch and change the Audio layout.
	* 	In Clover Configurator -> ACPI -> DSDT patches
	* Add Patches -> Added “HDAS to HDEF”
	* Under Devices -> Audio -> Inject -> 11.
	* Select the checkbox “ResetHDA”

## Vega 64 Fans were loud and GPU was overheating with minimal load for no apparent reason.
This was one of my major problems, but reportedly well documented.  I’m not certain why this happens, but the fix was fairly straightforward and documented in both these youtube tutorials.
[VEGA 56 and VEGA 64 GPU FAN Speed Fix Hackintosh| Step by Step | 2018 - YouTube](https://www.youtube.com/watch?v=IJQT6G3ZAY0)
[How To Fix AMD RX Vega GPU in macOS Mojave Hackintosh - YouTube](https://www.youtube.com/watch?v=nxnEbsWT4pU)

The key here was to download the file VegaTab_en.zip and create a kext file called Vegatab_FE.kext. This was copied into the _EFI_clover_kexts_other folder. I am not going to go over this in detail, since this is well described.

## FCPX and Preview cannot work properly due to unavailable iGPU hardware acceleration and unavailable Intel QuickSync.
The solution to this is rather problematic because doing one, enabling QuickSync and hardware acceleration breaks some less used features such as Netflix DRM in Safari or iTunes DRM. Since I am using this for video editing I focused on getting QuickSync enabled.

* In Clover Configurator, load up the config.plist file.
* In**ACPI**:
	* Click `List of Patches` and enable the following:
		* `Change GFX0 to IGPU`
* In**Devices**:
	* `SetInject` to 11. (This is for my motherboard)
	* Now to**properly**enable our headless iGPU, we need to fake the device id and `changeig-platform-id`. To do so, Click **Properties**, select `PciRoot(0x0)/Pci(0x2,0x0)`. Then, click the + button to add a property.
		* Add:
			* Property Key:`device-id`
			* Property Value:`923E0000`
			* Value Type: DATA

		* And add (or update if already present):
			* Property Key: `AAPL,ig-platform-id`
			* Property Value: `0300923E`
			* Value Type:DATA

## Getting iMessage, App Store, Hand Off, Continuity and Other Apple iServices to Work.
Full functionality of iMessage, App Store, iTunes, Handoff and Continuity is dependent on the functioning SMBIOS, Rt Variables and System Parameters. The idea is to setup a Mac Serial number that is **unique** and therefore can be linked exclusively to your iCloud account. 

1. In Clover Configurator, first mount the EFI partition of the boot drive.
2. Go to **Rt Variables** section.
3. Under the **ROM** section, you can leave this section to state `UseMacAddr0`. Alternatively, you can copy the MAC address of your En0 ethernet adapter and paste it here, in all lower case, without the colons. I chose to do the latter, although I am told that leaving `UseMacAddr0` accomplishes the same thing. 
4. Now pay attention to the BooterConfig and CsrActiveConfig. Leave the BooterConfig alone.  The CsrActiveConfig, refers to the functionality of **SIP (System Integrity Protection)**.  SIP protects your Mac from having malicious code injected, and protects the important areas most vulnerable to virus, hackware, ransomware and malware. 
5. You can Activate SIP by setting CsrActiveConfig to 0x00 to Deactivate SIP by setting it to 0x067. I prefer to keep it active in my final drive (SSD), but it **should remain inactive in a USB drive**.
6. Now navigate to the **SMBIOS** section in Clover Configurator.
7. Find the screen below and pay attention to the arrowheads (far right, under the buttons Model Lookup | Check Coverage.  Click that to open up and choose the Product Name closest to what you have. Because I have an i7-8700k I chose iMac 18,3.
8. Now, click as many times as possible on the **Generate New** button next to Serial Number.  The idea is to generate a serial number that fits your chosen Mac model, but is unique.
9. Once you are satisfied, click on **Check Coverage**, to go to the Apple Website to see if that model number is associated with any known Mac. Remember, _you ARE looking for an error message_ here stating that the iMac with the serial number you chose is not available. That is a good sign.
10. Once you have a unique serial number that nobody else has, click on **Model Lookup** to ensure that serial number does indeed correspond to the iMac type you chose under product name. This is an extra verification step.
11. Remember to click the checkbox that says **Trust** — so that this is trusted Mac serial.
12. That’s it. If you reboot the system now you should be able to setup your iCloud account and everything should work well. 


## I was unable to boot from USB but could boot from system SSD even when the EFI partition was copied from system SSD to USB drive : A lesson on SIP (Systems Integrity Protection). 
This particular problem was a lesson to me on how USB drives behave differently than a system SSD even with the same configuration. I stumbled upon this baffling error where, if I boot MacOS using the EFI partition in the system SSD, everything boots fine. But if I now copy that EFI partition to the USB drive and boot MacOS in the system SSD from the USB drive’s boot loader, right after the Apple Logo, the screen goes black and freezes with some pixelation. I found out, thanks to the help from cmn699 that this was because of SIP.  [Solved > - Cannot boot from USB drive after EFI partition from bootable SSD copied to USB… What am I missing? | tonymacx86.com](https://www.tonymacx86.com/threads/cannot-boot-from-usb-drive-after-efi-partition-from-bootable-ssd-copied-to-usb-what-am-i-missing.270730/#post-1900921) 

Apparently when SIP is enabled, the USB drive cannot act properly as the boot loader if the system is booting into an operating system residing elsewhere.  But it is not an issue if the OS and boot loader are on the same physical drive. Perhaps this is a protection mechanism. Once I disabled SIP in the USB drive, everything worked like a charm.


## USB drives do not work properly or USB 3.0 drives giving only USB 2.0 speeds.
This issue took me the longest to resolve, since I decidedly took the more challenging way of reading two really long, technically detailed articles about the issue. 

* A Guide to 10.11 USB Changes and Solutions by Rehabman [Guide 10.11+ USB changes and solutions | tonymacx86.com](https://www.tonymacx86.com/threads/guide-10-11-usb-changes-and-solutions.173616/) — Very important to understand how MacOS has changed how it accesses USB. An important primer to understand the next article which is quite complex.
* A Guide to Creating a Custom SSDT for USBInjectAll.kext [Guide Creating a Custom SSDT for USBInjectAll.kext | tonymacx86.com](https://www.tonymacx86.com/threads/guide-creating-a-custom-ssdt-for-usbinjectall-kext.211311/)

The gist of these two articles is that since 10.11 MacOS introduced new USB drivers that rely on ACPI much more intently than before. This means, that in order to properly use USB, the ACPI tables (DSDT) has to be very accurate. Unfortunately, this means that since various Hackintosh motherboards don’t have the same port configuration as any Mac, the ACPI tables that MacOS is looking for will be different that what is present in your computer.  So to subvert this issue, we can inject all available USB ports into the MacOS. This is what the famous _USBInjectAll.kext_ accomplishes. However, as of 10.14, MacOS also finalized a 15-port limit.  This seems like a lot until you realized that the 15 port limit includes USB2 and USB3, where USB2 counts as 1 port, and USB3 counts as 2 ports. So 15 ports isn’t all that much.

So the point is that you can get all of your ports active (albeit at slow speeds, at least was the case with me) with the USBInjectAll.kext, but in order to leverage the speeds from USB3 ports, we have to create a custom SSDT (ACPI table) to instruct the system accurately which ports are where and for what purpose they are used for.

The actual guide to doing this way too complicated for me to write here, so I will point to a few wonderful sources.  First and foremost, read the two articles linked above, the first one which underscores the problem, and the second one which teaches you how to use two pieces of software (IORegistryExplorer and MacIASL 2) to create SSDT which can be loaded on Clover Configurator.

The way to do this is explained in the article (A Guide to Creating a Custom SSDT for USBInjectAll.kext [Guide Creating a Custom SSDT for USBInjectAll.kext | tonymacx86.com](https://www.tonymacx86.com/threads/guide-creating-a-custom-ssdt-for-usbinjectall-kext.211311/)) but is also outlined in the Youtube video by Ibrahim Muslim. This is rather long winded but you will get a good feel for how to do this. 
Source: Ibrahim Muslim’s Youtube Guide on SSDT Patching [USB 3.0 & 3.1 Permanent FIX | SSDT Patch | PART 1 of 3| For All MacOS X | 10.14.1 USB fix - YouTube](https://www.youtube.com/watch?v=dFihvGaLmMQ&t=10s)  — There are 3 parts to this video.

I also found that CorpNewt had created an easy to use script called USBMap that enables you to map the USB ports and port configuration on your motherboard and you can create an SSDT using this script all automatically ([GitHub - corpnewt/USBMap: Py script for mapping out USB ports and creating a custom SSDT or injector kext (WIP).](https://github.com/corpnewt/USBMap))

There is a fabulous Youtube video from Carl Mercier demonstrating how to use corpnewts USBMap script to map out all the ports and create a custom SSDT. [How to fix USB 3 ports on a Hackintosh by generating your own SSDT or USBMap.kext - YouTube](https://www.youtube.com/watch?v=j3V7szXZZTc)

All of the above are great resources. I ended up using the manual method which uses IORegistryExplorer and MacIASL to get the job done. It took more time, but I felt like I learned a lot more testing it out piecemeal.  The result was great.  

If you are using the Gigabyte Z370 Aorus Gaming 5 motherboard, this is the port map I discovered.

	1. HS01/SS01 - Unknown
	2. HS02/SS02 - Bluetooth Device
	3. **HS03/SS03 - USB 3.0 DACUP Yellow (left)**
	4. **HS04 /SS04 - USB 3.0 DACUP Yellow (right)**
	5. **HS05/SS05 - USB 3.0 BLUE (left)**
	6. **HS06/SS06 - USB 3.0 BLUE (right)** 
	7. **HS07/SS07 - Front RIGHT USB (next to power switch)** 
	8. **HS08/SS08 - Front LEFT USB (next to indicators)** 
	9. HS09  - Internal USB2.0_2 motherboard header
	10. HS10 - Internal USB2.0_2 motherboard header
	11. **HS11 - Internal USB2.0_1 motherboard header**
	12. **HS12 - Internal USB2.0_1 motherboard header**
	13. **HS13 - USB 2.0 BLACK (left)**
	14. HS14 - USB 2.0 BLACK (right)
	15. USR1 - Unknown
	16. USR2 - Uknown

I have bold-faced above, the ports I decided to keep. 

HS03, SS03
HS04, SS04
HS05, SS05
HS06, SS06
HS07, SS07
HS08, SS08
HS11
HS12
HS13
==== 
Total number of active ports = 15

* Note that I disabled HS02/SS02 which is the internal Bluetooth. As soon as I disabled this, my Bluetooth card became fully operational since it was connected to the USB 2.0_1 motherboard header via an internal USB hub. 
* My motherboard has at least 2x USB-C connectors, which are not operational. Unfortunately, they are not intel USB controllers but are ASMedia controllers. Hoping that they may work, I also installed the USBGenericXHCI.kext file. We will have to see if it actually does.




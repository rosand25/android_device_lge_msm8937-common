======================================================================

To build information about iwlist, iwpriv, iwconfig etc, 

please visit the site of " https://github.com/nvamelichev/wireless-tools-android "  

======================================================================

■ In English 

You should download this open source from 'https://github.com/nvamelichev/wireless-tools-android' to compile by arm-linux-androideabi.

* explanation of build method in English. 

 1. build environment : choose "Ubuntu 64bit" ( Android 6.0 has to be compiled.) 


 2. build command  : under the directory 'wireless-tools-android', execute 'mm' command to build iwlist.


======================================================================

■ In Korean  

* 컴파일 방법에 대한 설명 : 이 공개 소스는 아래 https://github.com/nvamelichev/wireless-tools-android를 모두 다운로드 후,

android 6.0에 포함되어 있는 arm compiler(prebuilts/gcc/linux-x86/arm/arm-linux-androideabi)를 이용해 생성하였음


 1. 빌드 환경 : Ubuntu 64bit (Android 6.0이 빌드된 상태) 

 2. 빌드 명령 : 다운로드한 wireless-tools-android 디렉토리에서 mm 명령을 실행하면 iwlist가 생성됨

======================================================================



Wireless Tools & IfRename
	-------------------------

	This package contains the Wireless tools, used to manipulate
the Wireless Extensions. The Wireless Extensions is an interface
allowing you to set Wireless LAN specific parameters and get the
specific stats.
	It also contains the IfRename package, used for advance
renaming of network interfaces.

web page :
--------
	You'll find a lot of useful info on :
		http://www.hpl.hp.com/personal/Jean_Tourrilhes/Linux/Tools.html
		http://web.hpl.hp.com/personal/Jean_Tourrilhes/Linux/

Precompiled version :
-------------------
	Most Linux distributions offer precompiled package containing
these tools. And many of them preinstall them by default. On the other
hand, installation of this package is (now) easy and allows you to get
a more up-to-date version.

INSTALL
-------
	This file contains installation instructions and requirements.
	A *must*-read.

DISTRIBUTION.txt
----------------
	This file documents how to configure wireless cards at
boot time with various Linux distributions (using Wireless
Extensions). Please read it carefully before asking questions.
	In this file, I try to collect all the specifics of Wireless
Extensions integration in the most common Linux distributions. I need
your help to complete this file.

HOTPLUG.txt
-----------
	This file documents how to manage and configure removable
wireless cards using Hotplug. This is more advanced than the simple
procedures of DISTRIBUTION.txt. This is currently mostly Debian
specific, but I hope you will contribute for other distributions.

PCMCIA.txt
----------
	This file describes how to use PCMCIA init script to configure
Wireless Extensions and how to use PCMCIA schemes.

man pages (iwconfig.8, iwlist.8, iwpriv.8, iwspy.8)
---------
	VERY IMPORTANT : I try to keep the man pages up to date, so
you'd better read them before asking questions.
	ALSO IMPORTANT : Those man pages describe the capacities of
the tools, no device implements the full range (and drivers usually
implement even less).

	As far as I know, the man pages are the most complete, up to
date and accurate documentation of the wireless tools. An update of
the web page related to Wireless Extensions is long overdue. Send
feedback to me.
	The man pages can either be copied into a location where the
command "man" will find them, such as /usr/local/man/man8, or can be
read locally with the command :
		nroff -man xxx.8 | less

localised man pages (fr/*)
-------------------
	Localised man pages are not made by me, therefore the only
localisations available are those sent to me by courageous volonteers,
and I expect those man pages to 'lag' compared to the english
version (i.e. not have all the latest updates). Translating man pages
is not a very gratifying task, especially due to my broken english,
and many technical terms don't translate well to other languages, so
refer to the english version when in doubt.

iwconfig.c
----------
	The main wireless tool. Used for device configuration and to see
the most common wireless parameters.

iwlist.c
--------
	Display some large chunk of information not displayed by iwconfig.
	For example, all bit rates, all frequencies, all keys...

iwspy.c
-------
	Mobile IP support test and allows to get stats per MAC
address (instead of globally). Also, for some drivers/devices, this is
the only way to get stats in Ad-Hoc mode.

iwpriv.c
--------
	Manipulate driver private ioctls : all parameters that are
specific to a driver or a device and therefore not part of iwconfig.

iwgetid.c
---------
	Output the ESSID or NWID of the specified device.
	Can also output it in a form that can be used as a PCMCIA Scheme.

iwevent.c
---------
	Display Wireless Events. Most recent drivers will support this
relatively new feature, but some older drivers may not support it.

ifrename.c :
----------
	Rename network interfaces based on various selectors.

iwlib.c
-------
	The Wireless Tools helper library. May be useful if you want
to create your own applications using Wireless Extensions.

iwmulticall.c
-------------
	Multicall version of the tools for embedded systems.

Changelog, contributions :
------------------------
	See CHANGELOG.h

wireless.h
----------
	Definition of the Wireless Extensions. Remember that the
definition used by the drivers and the tools must match, otherwise
funny things may happen. The tools try to check for that.
	Since Wireless Extensions v12, you can no longer drop this
file into your kernel headers to update the Wireless Extensions, you
need to use the full patches available on my web page. So, the use is
more if you plan to do some cross compile or something similar.
	Just for your enjoyment, there are various releases of it. If
your kernel/drivers are old, you may want to try the older releases...

sample_xxx.c :
------------
	Various samples of code showing how to implement some of the
more tricky features of Wireless Extensions in your driver.
	Note that there is no guarantee that this code compiles, let
alone works, but it should point you in the proper direction.
	Also, have a look at existing drivers in the Linux kernel.

19-udev-ifrename.rules :
----------------------
	udev rules to integrate properly ifrename (udev >= 107).

Other tools :
-----------
	My web page lists many other tools using Wireless
Extensions that you may find useful...
	http://www.hpl.hp.com/personal/Jean_Tourrilhes/Linux/Tools.html#links

Other questions :
---------------
	You have the source, and it is documented. In 99% of cases,
you will find your answer there.

	Good luck...

	Jean <jt@hpl.hp.com>
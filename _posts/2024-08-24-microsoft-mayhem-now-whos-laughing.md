---
title: "Microsoft Mayhem: Now who's laughing?"
date: 2024-08-24
categories: 
  - "home"
  - "tech"
tags: 
  - "arch"
  - "bios"
  - "crowdstrike"
  - "gentoo"
  - "knowledge-base"
  - "microsoft"
  - "mocaccinoos"
  - "operating-system"
  - "sabayon"
  - "secure-boot"
  - "windows"
  - "windows-11"
  - "wsl"
coverImage: "/sudovid-blog/images/ms.png"
---

The recent _**CrowdStrike**_ update that caused mayhem around the PC world resulted in the loss of several billions of dollars for some organizations. Some will take matters to the court while some will continue to pamper _**CrowdStrike**_ for security bullshit. Personally, I don’t hate security but I hate the idea when it becomes a limiting factor for overall functioning of the software. While we are at it, we need to discuss the underlying factor on which security hue and cry is made up. It’s the operating system that we don’t trust and try to secure with unnecessary applications. And, what’s the common denominator in all of them? _**Microsoft Windows**_!

I am too guilty of sticking with it, especially for the last five years. But, why is that so? Let’s break it down for the sake of simplicity. Any operating system that updates or upgrades itself without a tested package is a cause of concern. And for that purpose, I had used **Gentoo** for a long time and a pretty stable one called [_**Sabayon**_](https://en.wikipedia.org/wiki/Sabayon_Linux). Unfortunately, that project got shut down sometime in 2019 and had pushed me into the wilderness of poking around with other distributions. Just because I don’t like **Debian-based** operating systems and **Arch** seems to be always unstable, I finally made amends with **Microsoft Windows 11**. They offered _**Windows Subsystems for Linux (WSL)**_ right under their hood and gave me a choice for using _**GNU/Linux**_ from within the _Windows_ system. I mean what more I could have asked for. But, what I didn’t realize is that the entire world including some of the crucial government and public services too made that shift. I mean not from _Linux_ to _Windows_ but to _**Windows 11**_ itself. Though it didn’t seem like a bad decision initially, the recent events opened a whole new debate around its stability again.

_**CrowdStrike**_ is not an isolated incident and you might be surprised to note that there are several other critical known issues that have caused concerns among _**Microsoft Windows**_ users. People who are using the **Windows 11** versions **21H2**, **22H2**, or **23H2** are all impacted by it.

[![Microsoft OS Known Issues](https://github.com/mrsauravs/opinion/raw/main/assets/images/microsoft-issues.png "Critical Known Issues")](https://github.com/mrsauravs/opinion/blob/main/assets/images/microsoft-issues.png)

The last issue that happened a few days back affected a few Linux enthusiasts who love to dual or triple boot their systems with _**Microsoft Windows**_. This latest issue causes the **GRUB** bootloader to freeze and prevent other operating systems to boot that have not been signed for the secure boot. _**Secure Boot**_ is in fact a _**Microsoft**_ invention enforced at the **BIOS** level. It had its fair share of debate in the past and has forced _**Microsoft**_ to give an option to disable it too. But, the latest update nullifies it again.

Ironically, what has saved me (or a lucky bunch of a few more users) so far is another critical _**Windows**_ known issue that causes updates to not finish and get stuck at 96%. So, those lucky users never see the light and plight of these known issues. In fact, if you read the **KB** articles on **_Microsoft_** site, they too recommend removing this update as a workaround. This brings us to the same debate that I pointed out in my last article: Lack of proper testing and wildly pushing the updates. _**Microsoft,**_ just like _**CrowdStrike**_, too displaced a whole bunch of their testing staff in the last few months.

The willy-nilly firing of the staff in these organizations for whatever justifiable reasons is a matter of concern. While we don’t have a say in that, we definitely can take matters into our hands too! As your friend from the open community, I would suggest we start supporting open-source projects more and unburden ourselves from the corporate controlled software. One such recommendation is [_**MocaccinoOS**_](https://www.mocaccino.org/) that you should switch to right now. This project is branched out from _**Sabayon**_ and therefore would be an ideal choice to bring back stability to its core.

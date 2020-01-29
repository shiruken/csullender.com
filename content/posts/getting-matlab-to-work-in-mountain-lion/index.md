---
title: 'Getting MATLAB to work on Mac OS X 10.8 ''Mountain Lion'''
date: Wed, 01 Aug 2012 15:36:59 +0000
draft: false
tags: ['Apple', 'Software', 'Tips & Tricks']
---

One of the biggest risks of immediately upgrading to a new operating system is the loss of functionality for vital programs. While developers will scramble to get their apps ready for the sweeping changes oft accompanied by an upgrade to an operating system, it is inevitable that bugs/quirks/errors will surface. As an engineering graduate student, one of the programs I use quite frequently is [MATLAB](http://www.mathworks.com/products/matlab/), which is built upon the X11 window system for the Apple OS environment. In the latest update to OS X, [Apple decided to remove X11](http://support.apple.com/kb/HT5293) in favor of an open-source development called XQuartz. What this means is that if you upgrade to Mountain Lion, MATLAB cannot run because X11 is no longer included in the operating system. While I'm sure many will complain about Apple's apparent lack of support for one of the most commonly used technical programs, they did not truly abandon X11. Rather, they have provided development support to the [XQuartz project](http://xquartz.macosforge.org/landing/) which is effectively an updated version of X11 which was first included in Mac OS X 10.5.

![XQuartz Logo](XQuartz.jpg)

When you attempt to launch MATLAB in Mountain Lion, you should be prompted to install X11, which has now been repackaged as XQuartz and developed as an open-source project ([Download Link](http://xquartz.macosforge.org/landing/)). Once you've downloaded and installed the X11-replacement, you'll need to restart your computer to set XQuartz as the default X window system. You might also need to install the Java SE 6 runtime, which will be done through Software Update, before you can get MATLAB open. So far, MATLAB 2011b seems to be working flawlessly on my MacBook Pro running Mountain Lion. I assume that 2012a will also work correctly although I have no support for this claim.

**Update:** MATLAB will work in OS X 10.8 'Mountain Lion' with the installation of XQuartz
---
title: Ubuntu Default Audio Device
author: pt1602
type: post
date: 2021-04-15T05:55:41+00:00
url: /ubuntu-default-audio-device/
categories:
  - linux
  - ubuntu
tags:
  - audio
  - device
  - input
  - linux
  - output
  - ubuntu

---
I searched for the awnser a little and found this: https://itectec.com/ubuntu/ubuntu-how-do-you-set-a-default-audio-output-device-in-ubuntu-18-04/

Gonna save this here, because I am going to search it one day again.

  1. Run:&nbsp;`pactl list short sinks`
  2. Note the device name you want to use as default
  3. Try to run:&nbsp;`pactl set-default-sink <Your_Device_Name>`  
    This should work without giving you an error message.
  4. Open the application &#8220;Startup Applications&#8221; (Should be preinstalled on Ubuntu)
  5. Click on &#8220;Add&#8221;
  6. Give your startup item a name
  7. Copy your command from above into the command field:  
    `pactl set-default-sink 'Your-Device-Name'`
  8. Click on &#8220;Save&#8221;.
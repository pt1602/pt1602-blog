---
title: Windows 10 settings wont open
author: pt1602
type: post
date: 2020-05-25T14:59:09+00:00
url: /windows-10-settings-wont-open/
categories:
  - bugs
  - everything
  - windows10
tags:
  - 10
  - does not open
  - open
  - setting
  - settings
  - system
  - system settings
  - windows
  - windows ten
  - windows10
  - wont

---
Run this in the commad prompt:

> PowerShell -ExecutionPolicy Unrestricted -Command &#8220;& {$manifest = (Get-AppxPackage \*immersivecontrolpanel\*).InstallLocation + &#8216;\AppxManifest.xml&#8217; ; Add-AppxPackage -DisableDevelopmentMode -Register $manifest}&#8221;
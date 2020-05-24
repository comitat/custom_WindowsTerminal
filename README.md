# customize the new Windows Terminal

[![Windows Terminal](https://inc-news.ru/data/inc/preview/2019-06/23/image-3962-1561289454-240x160.png)](https://github.com/microsoft/terminal)

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://github.com/microsoft/terminal/releases)

The Windows Terminal is a new, modern, fast, efficient, powerful, and productive terminal application for users of command-line tools and shells like Command Prompt, PowerShell, and WSL.

![alt text](https://g-ek.com/assets/images/windows-terminal/windows-terminal.jpg)

### Settings

  **the directory**: 
  ```sh
  %USERPROFILE%\AppData\Local\Packages\Microsoft.WindowsTerminal_8wekyb3d8bbwe\LocalState
```

To change the background of any of the shells, you first need to put the image file in a place that the terminal application can read.Windows Terminal is a Universal Windows Platform (UWP) application, so it prefers to use its own AppData folder. 
AppData is a folder that you usually find in your user profile, and it is used to store program settings. UWP apps create a custom AppData folder and use It instead. The Windows terminal AppData folder is located in the following path:
```sh
%LOCALAPPDATA%\Packages\Microsoft.WindowsTerminal_8wekyb3d8bbwe\RoamingState
```
To change the background image for one of these sections, add the following lines under the "icon" line or above the "name" line:

>"backgroundImage" : "ms-appdata:///roaming/image.jpg",
>"backgroundImageOpacity" : 0.75,
>"backgroundImageStrechMode" : "fill",

#### Change hotkeys

>{
 "command" : "closeTab",
 "keys" : 
 [
 "ctrl+w"
 ]
 },




* [gist user kasuken](https://gist.github.com/kasuken/076d68b92e2a67dfda591587c77a40c0#file-profiles-json) - good profiles settings user kasuken on GitHub.


#### Problems

**`Microsoft.PowerShell_profile.ps1 cannot be loaded because running
scripts is disabled on this system.`**

As an *Administrator*, you can set the execution policy by typing this into your PowerShell window:
```sh
Set-ExecutionPolicy RemoteSigned
```

**`LF will be replaced by CRLF in`**

Run the following command to git to convert all CRLF line endings to LF before it stores it in the commit:
>$ git config --global core.autocrlf input

Run the following command to prevent git from adding updates whose only function was to change the line-ending:
>git config --global core.safecrlf true
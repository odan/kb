---
layout: default
title: Linux Software
published: true
parent: Linux
---

# Linux Software

## Enable snapd

On Linux Mint 20, /etc/apt/preferences.d/nosnap.pref needs to
be removed before Snap can be installed. This can be accomplished from the command line:

```
sudo rm /etc/apt/preferences.d/nosnap.pref
sudo apt update
sudo apt install snapd
```

## PhpStorm

PhpStorm is available in the Software Manager, but the Setup will not work.
For this reason I prefer to install it manually.
To install PhpStorm, simply use the following command:

```
sudo snap install phpstorm --classic
```

Change keyboard shortcut for `xflock4` to `Shift+Ctrl+L`

### PhpStorm Themes

* <https://github.com/odan/phpstorm-color-schemes>
* [Github 3 Theme for PhpStorm](https://plugins.jetbrains.com/plugin/12271-github-3-color-scheme)
* [Photon color Theme for PhpStorm](https://github.com/brendt/phpstorm-photon-theme)

```
su user
cd ~/Downloads
wget https://raw.githubusercontent.com/brendt/phpstorm-photon-theme/master/Photon%20-%20Dark.icls -O Photon-Dark.icls
wget https://raw.githubusercontent.com/brendt/phpstorm-photon-theme/master/Photon%20-%20Light.icls -O Photon-Light.icls
```

### PhpStorm Plugins


## Google Chrome

To install Google Chrome, run the following:

```
cd ~/Downloads
sudo apt install libxss1 libappindicator1 libindicator7
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
sudo apt install ./google-chrome-stable_current_amd64.deb -y
```

If error messages pop up after running the command sudo apt install ./google-chrome*.deb then run the command

```
sudo apt install -f.
```

If you want to install **Chromium** instead, run:

```
sudo snap install chromium
```

or use apt:

```
sudo apt install chromium-browser chromium-browser-l10n chromium-codecs-ffmpeg 
```

## Fonts

**Microsoft Fonts, Arial, Verdana etc**

```
sudo apt install ttf-mscorefonts-installer rar unrar libavcodec-extra gstreamer1.0-libav gstreamer1.0-plugins-ugly gstreamer1.0-vaapi
```

Segoe UI font, however, is not part of the ttf-mscorerfonts package.
To install the full pack of Segoe UI fonts run:

```
sudo su
mkdir -p /usr/share/fonts/truetype/
cd /usr/share/fonts/truetype/
wget -q https://github.com/martinring/clide/blob/master/doc/fonts/segoeui.ttf?raw=true -O segoeui.ttf
wget -q https://github.com/martinring/clide/blob/master/doc/fonts/segoeuib.ttf?raw=true -O segoeuib.ttf
wget -q https://github.com/martinring/clide/blob/master/doc/fonts/segoeuib.ttf?raw=true -O segoeuii.ttf
wget -q https://github.com/martinring/clide/blob/master/doc/fonts/segoeuiz.ttf?raw=true -O segoeuiz.ttf
wget -q https://github.com/martinring/clide/blob/master/doc/fonts/segoeuil.ttf?raw=true -O segoeuil.ttf
wget -q https://github.com/martinring/clide/blob/master/doc/fonts/seguili.ttf?raw=true -O seguili.ttf
wget -q https://github.com/martinring/clide/blob/master/doc/fonts/segoeuisl.ttf?raw=true -O segoeuisl.ttf
wget -q https://github.com/martinring/clide/blob/master/doc/fonts/seguisli.ttf?raw=true -O seguisli.ttf
wget -q https://github.com/martinring/clide/blob/master/doc/fonts/seguisb.ttf?raw=true -O seguisb.ttf
wget -q https://github.com/martinring/clide/blob/master/doc/fonts/seguisbi.ttf?raw=true -O seguisbi.ttf
fc-cache -frv
```

**IBM Plex Mono** *for PhpStorm*

```
sudo su
mkdir -p /usr/share/fonts/truetype/
cd /usr/share/fonts/truetype/
wget -q https://raw.githubusercontent.com/IBM/plex/master/IBM-Plex-Mono/fonts/complete/ttf/IBMPlexMono-Bold.ttf -O IBMPlexMono-Bold.ttf
wget -q https://raw.githubusercontent.com/IBM/plex/master/IBM-Plex-Mono/fonts/complete/ttf/IBMPlexMono-BoldItalic.ttf -O IBMPlexMono-BoldItalic.ttf
wget -q https://raw.githubusercontent.com/IBM/plex/master/IBM-Plex-Mono/fonts/complete/ttf/IBMPlexMono-ExtraLight.ttf -O IBMPlexMono-ExtraLight.ttf
wget -q https://raw.githubusercontent.com/IBM/plex/master/IBM-Plex-Mono/fonts/complete/ttf/IBMPlexMono-ExtraLightItalic.ttf -O IBMPlexMono-ExtraLightItalic.ttf
wget -q https://raw.githubusercontent.com/IBM/plex/master/IBM-Plex-Mono/fonts/complete/ttf/IBMPlexMono-Italic.ttf -O IBMPlexMono-Italic.ttf
wget -q https://raw.githubusercontent.com/IBM/plex/master/IBM-Plex-Mono/fonts/complete/ttf/IBMPlexMono-Light.ttf -O IBMPlexMono-Light.ttf
wget -q https://raw.githubusercontent.com/IBM/plex/master/IBM-Plex-Mono/fonts/complete/ttf/IBMPlexMono-LightItalic.ttf -O IBMPlexMono-LightItalic.ttf
wget -q https://raw.githubusercontent.com/IBM/plex/master/IBM-Plex-Mono/fonts/complete/ttf/IBMPlexMono-Medium.ttf -O IBMPlexMono-Medium.ttf
wget -q https://raw.githubusercontent.com/IBM/plex/master/IBM-Plex-Mono/fonts/complete/ttf/IBMPlexMono-MediumItalic.ttf -O IBMPlexMono-MediumItalic.ttf
wget -q https://raw.githubusercontent.com/IBM/plex/master/IBM-Plex-Mono/fonts/complete/ttf/IBMPlexMono-Regular.ttf -O IBMPlexMono-Regular.ttf
wget -q https://raw.githubusercontent.com/IBM/plex/master/IBM-Plex-Mono/fonts/complete/ttf/IBMPlexMono-SemiBold.ttf -O IBMPlexMono-SemiBold.ttf
wget -q https://raw.githubusercontent.com/IBM/plex/master/IBM-Plex-Mono/fonts/complete/ttf/IBMPlexMono-SemiBoldItalic.ttf -O IBMPlexMono-SemiBoldItalic.ttf
wget -q https://raw.githubusercontent.com/IBM/plex/master/IBM-Plex-Mono/fonts/complete/ttf/IBMPlexMono-Text.ttf -O IBMPlexMono-Text.ttf
wget -q https://raw.githubusercontent.com/IBM/plex/master/IBM-Plex-Mono/fonts/complete/ttf/IBMPlexMono-TextItalic.ttf -O IBMPlexMono-TextItalic.ttf
wget -q https://raw.githubusercontent.com/IBM/plex/master/IBM-Plex-Mono/fonts/complete/ttf/IBMPlexMono-Thin.ttf -O IBMPlexMono-Thin.ttf
wget -q https://raw.githubusercontent.com/IBM/plex/master/IBM-Plex-Mono/fonts/complete/ttf/IBMPlexMono-ThinItalic.ttf -O IBMPlexMono-ThinItalic.ttf
fc-cache -frv
```

## Adobe Reader

Use Google Chrome as PDF viewer

## VSCode

### VSCode Plugins

## Inkscape

```
sudo apt install inkscape -y
```

## XnView

*Alternative to IrfanView*

```
wget https://download.xnview.com/XnViewMP-linux-x64.deb
sudo dpkg -i XnViewMP-linux-x64.deb
```
<https://www.xnview.com/en/xnviewmp/>

## SQLYog

Downloads: <https://github.com/webyog/sqlyog-community/wiki/Downloads>

```
sudo apt install wine-stable
wget https://s3.amazonaws.com/SQLyog_Community/SQLyog+13.1.9/SQLyog-13.1.9-0.x64Community.exe
sudo wine SQLyog-13.1.9-0.x64Community.exe
```

## Microsoft Teams

Download: <https://www.microsoft.com/de-de/microsoft-teams/download-app#desktopAppDownloadregion>

```
wget https://packages.microsoft.com/repos/ms-teams/pool/main/t/teams/teams_1.4.00.13653_amd64.deb
sudo dpkg -i teams_1.4.00.13653_amd64.deb
```

## OBS Studio

```
sudo apt install ffmpeg
sudo add-apt-repository ppa:obsproject/obs-studio
sudo apt install obs-studio
```

## Pandoc

```
sudo apt install pandoc
```

## MiKTeX

Download: <https://miktex.org/download>

```
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys D6BC243565B2087BC3F897C9277A7293F59E4889
echo "deb http://miktex.org/download/ubuntu focal universe" | sudo tee /etc/apt/sources.list.d/miktex.list
sudo apt update
sudo apt install miktex
```

## Uninstall Software

```
# LibreOffice
sudo apt remove --purge -y libreoffice*
sudo apt remove --purge -y libjuh*

# Remove all LibreOffice start menu icons
sudo find ~/.local/share/applications/ -type f -name '*libreoffice*.desktop' -delete

# Gimp
sudo apt remove --purge -y gimp

# Thunderbird
sudo apt remove --purge -y thunderbird

sudo apt clean
sudo apt autoremove
```

## Powerline Shell

<https://github.com/b-ryan/powerline-shell>

```
sudo apt install python3-pip
sudo pip install powerline-shell
sudo apt install fonts-powerline
```

Add the following to your .bashrc file:

```
vim ~/.bashrc
```

Scroll down, press "a" and add this: 

```
function _update_ps1() {
    PS1=$(powerline-shell $?)
}

if [[ $TERM != linux && ! $PROMPT_COMMAND =~ _update_ps1 ]]; then
    PROMPT_COMMAND="_update_ps1; $PROMPT_COMMAND"
fi
```

Press escape, enter: `:qw!` to save the file.

Open a new console window.

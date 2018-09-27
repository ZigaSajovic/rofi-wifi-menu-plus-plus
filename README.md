# rofi-wifi-menu++

An enhanced rofi menu for managing WiFi connections.

This menu was written to enhance the functionalities of [rofi-wifi-menu](https://github.com/zbaylin/rofi-wifi-menu). The original implementation lacked functionalities, which seemed crucial to the author. Note that the [theming](https://github.com/DaveDavenport/rofi-themes) of rofi is left to the user; see [usage](#usage).
## Features

A birds eye view of provided features:

  * toggle WiFi
  * connecting to existing wifi connections
  * creation of wifi connections to discovered networks of various security protocols
    * None
    * WEP
      * password
    * WPA/WPA2
      * password
    * 802.1X
      * identity
      * password
  * manual creation of wifi connections (ex. for hidden networks)
    * NOTE: if one already exists for the manually entered SSID, the user is simply connected to it, and a duplicate is not created
  * correct handling of cases where the user has multiple options
    * multiple existing connections for the same SSID usually labelled <SSID> <num>, by the Network Manager
    * multiple wifi devices on the machine

## Selecting a discovered network

When the user selects a discovered network, the script first checks if there already exists a connection with a matching name. If one does, the user is connected to it and the menu exits. If there are multiple existing connections for the same SSID, usually labeled \<SSID\> \<num\>, the user is prompted with a menu for selecting one of them. If the connection does not exist, the user is guided through the process of creating it; different forms of securities have different procedures. Upon completion, the user is connected. If multiple WiFi devices are present, the user is prompted to choose one.

## Usage

The script is to be run with a parameter, which specifies the path to the rofi theme to be used. Provided on the repo is a simple config, emulating the dmenu theme.

    ./rofi_wifi_menu /path/to/rofi/theme.rasi

## Requirements 

  * [Rofi](https://github.com/DaveDavenport/rofi)
  * [Network Manager](https://wiki.gnome.org/Projects/NetworkManager)

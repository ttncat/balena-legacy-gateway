# LoRaWAN (Legacy) UDP Packet Forwarder App for BalenaOS

This project deploys a LoRaWAN gateway with UDP Packet Forward protocol using Docker or Balena.io. It runs on a PC, a Raspberry Pi 3/4, Compute Module 3/4 or balenaFin with SX1301, SX1302, SX1303 or SX1308 LoRa concentrators (e.g. RAK831, RAK833, RAK2245, RAK2247, RAK2287, RAK5146, Seeed WM1302 and IMST iC880a among others).

## Introduction

Deploy a LoRaWAN Gateway running the Legacy UDP Packet Forwarder as a balena.io fleet.

Main features:

* Support for AMD64 (x86_64), ARMv8 and ARMv7 architectures.
* Support for SX1301, SX1302, EX1303 and SX1308 concentrators.
* Almost one click deploy and at the same time highly configurable.

Components used:

* [UDP Packet Forwarder](https://github.com/RAKWireless/udp-packet-forwarder)
* [WiFi-Connect](https://github.com/balena-os/wifi-connect)

Check the differents repos for specific configuration options.


## Deploy

### Via [Balena Deploy](https://www.balena.io/docs/learn/deploy/deploy-with-balena-button/)

Running this project is as simple as deploying it to a balenaCloud application. You can do it in just one click by using the button below:

[![balena deploy button](https://www.balena.io/deploy.svg)](https://dashboard.balena-cloud.com/deploy?repoUrl=https://github.com/ttncat/balena-legacy-gateway)

Follow instructions, click **Add a Device** and flash an SD card with that OS image dowloaded from balenaCloud. Enjoy the magic 🌟Over-The-Air🌟!


### In-control deploy via [Balena-Cli](https://www.balena.io/docs/reference/balena-cli/)

If you are a balena CLI expert, feel free to use balena CLI. This option lets you configure in detail some options, like adding new services to your deploy or configure de DNS Server to use.

- Sign up on [balena.io](https://dashboard.balena.io/signup)
- Create a new application on balenaCloud.
- Add a new device and download the image of the BalenaOS it creates.
- This is the moment to configure the DNS server in the BalenaOS if required. See the `Configuring the domain` section  below.
- Burn and SD card (if using a Pi), connect it to the device and boot it up.

While the device boots (it will eventually show up in the Balena dashboard) we will prepare de services:

- Clone this repository to your local workstation. Don't forget to update the submodules.
```
cd ~/workspace
git clone https://github.com/ttncat/balena-legacy-gateway
cd standalone-lorawan-gateway-balena
```
- Edit services by editing the `docker-compose.yml` file
- Using [Balena CLI](https://www.balena.io/docs/reference/cli/), push the code with `balena push <application-name>`
- See the magic happening, your device is getting updated 🌟Over-The-Air🌟!


## License

The contents of this repository (not of those repositories linked or used by this one) are under BSD 3-Clause License.

Copyright (c) 2022 Xose Pérez <xose.perez@gmail.com> for TTN Catalunya
All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

1. Redistributions of source code must retain the above copyright notice,
   this list of conditions and the following disclaimer.
2. Redistributions in binary form must reproduce the above copyright
   notice, this list of conditions and the following disclaimer in the
   documentation and/or other materials provided with the distribution.
3. Neither the name of this project nor the names of its
   contributors may be used to endorse or promote products derived from
   this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE
ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT OWNER OR CONTRIBUTORS BE
LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR
CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF
SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS
INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN
CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE)
ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE
POSSIBILITY OF SUCH DAMAGE.

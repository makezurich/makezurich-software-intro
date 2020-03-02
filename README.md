# #MakeZurich software intro
Introduction to software and platforms available at [MakeZurich.ch](http://makezurich.ch/).

Found a bug or have a question? [Submit an issue](../../issues).

## Internet of Things
Here's a simple reference model for Internet of Things (IoT) applications:

<img src="iot.jpg" width="540"/>

For a general introduction to IoT, see [this presentation](http://www.tamberg.org/fhnw/2019/hs/IoT01Introduction.pdf).

## Device
A device contains a microcontroller, connectivity and sensors or actuators.

To create a custom device, read the [#MakeZurich hardware intro](https://github.com/make-zurich/makezurich-hardware-intro).

## Connectivity
Connectivity options include [Bluetooth Low Energy](https://learn.adafruit.com/introduction-to-bluetooth-low-energy/introduction) (BLE) and [LoRaWAN](https://lora-alliance.org/about-lorawan).

[The Things Network](https://www.thethingsnetwork.org/) (TTN) is a global, open LoRaWAN infrastructure.

## Gateway
A gateway forwards data from a device to the backend and vice versa.

### The Things Network LoRaWAN gateway
In Zürich [there are plenty of TTN LoRaWAN gateways](https://www.thethingsnetwork.org/community/zurich/) already.

To check if there's network coverage, use the [TTN mapper](https://ttnmapper.org/).

You can also [build](https://www.thingiverse.com/thing:1665467) or buy a [indoor](https://www.thethingsnetwork.org/docs/gateways/thethingsindoor/) or [outdoor](https://www.lorixone.io/) gateway.

### Raspberry Pi as a BLE gateway
See [this tutorial](http://www.tamberg.org/fhnw/2019/hs/IoT06RaspberryPiGateway.pdf) based on the [Zero W](https://www.raspberrypi.org/products/raspberry-pi-zero-w/).

## Backend
The backend server provides a service endpoint in the cloud.

Devices send data to the backend, or receive commands.

Clients get data from the backend, or send commands.

### The Things Network LoRaWAN backend
> Crash course: [LoRaWAN and TTN](https://makezurich.ch/), March 23, 7pm at the Smart City Lab Zürich.

The TTN LoRaWAN backend provides access to data sent by your devices, here's a [system overview](https://www.thethingsnetwork.org/docs/).

To send data, [sign up for a TTN account](https://account.thethingsnetwork.org/register), open the [EU](https://console.thethingsnetwork.org/) or [Swiss console](https://console.ttn.opennetworkinfrastructure.org/), create an application and add your device.

### Accessing your data

Messages are received/sent to/from the application side via [MQTT](https://www.thethingsnetwork.org/docs/applications/mqtt/). There are plenty of MQTT libraries for every language. Additionally, there are specific wrappers/libraries for TTN that simplify access to the data streams.

- [Node-RED](https://www.thethingsnetwork.org/docs/applications/nodered/)
- [Python](https://www.thethingsnetwork.org/docs/applications/python/)
- [Node.js](https://www.thethingsnetwork.org/docs/applications/nodejs/)
- [Java](https://www.thethingsnetwork.org/docs/applications/java/)
- [Go](https://www.thethingsnetwork.org/docs/applications/golang/)

### Hosting on virtual machines
[Datacenter Light](https://datacenterlight.ch/) provides free Linux virtual machines (VM) during #MakeZurich, to host your backend.

Contact [support@ungleich.ch](mailto:support@ungleich.ch) with the subject *MakeZurich VM* and specify what you need:

How many CPU cores (1..8), RAM size (1..16) GB, SSD size (10..50) GB and if you require native IPv4 (yes/no).

## Client

### Web app
TODO

### Android app 
TODO

### iOS app
TODO

## License
This tutorial by [MakeZurich.ch](http://makezurich.ch/) is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).

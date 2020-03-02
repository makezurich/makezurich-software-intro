# #MakeZurich software intro
Introduction to software and platforms available at [MakeZurich.ch](http://makezurich.ch/).

Found a bug or have a question? [Submit an issue](../../issues).

## Internet of Things
Here's a simple reference model for Internet of Things (IoT) applications:

<img src="iot.jpg" width="540"/>

For an introduction to IoT, see [this presentation](http://www.tamberg.org/fhnw/2019/hs/IoT01Introduction.pdf).

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


### The Things Network LoRaWAN backend
Check [docs and examples](https://www.thethingsnetwork.org/docs/).

 - Network server: there is a global network server, and additionally, the Swiss communities operate a local network server (interconnected to the global one). Check the [global console](https://console.thethingsnetwork.org/) and the [swiss console](https://console.ttn.opennetworkinfrastructure.org/).
 - Application: this is where you receive the data from your sensor and store it/visualize it/etc.

More details about LoRaWAN: `Crash course: LoRaWAN and The Things Network`, March 23rd, 19:00 at SmartCity-Lab.

### Accessing your data

Messages are received/sent to/from the application side via [MQTT](https://www.thethingsnetwork.org/docs/applications/mqtt/). There are plenty of MQTT libraries for every language. Additionally, there are specific wrappers/libraries for TTN that simplify access to the data streams.

- [Node-RED](https://www.thethingsnetwork.org/docs/applications/nodered/)
- [Python](https://www.thethingsnetwork.org/docs/applications/python/)
- [Node.js](https://www.thethingsnetwork.org/docs/applications/nodejs/)
- [Java](https://www.thethingsnetwork.org/docs/applications/java/)
- [Go](https://www.thethingsnetwork.org/docs/applications/golang/)

### Hosting on Virtual Machines

If you need hosted virtual machines to run your application, [datacenter light](https://datacenterlight.ch/) offers free VMs during MakeZurich (running on 100% renewable energy). Send an email to [support@ungleich.ch](mailto:support@ungleich.ch) with the subject `MakeZurich VM` and specify the VM that you need for the event:

- cpu cores (1..8)
- ram (1..16) gb
- ssd size (10..50) gb
- native ipv4 required (yes/no)

## Client

### Web app
TODO

### Android app 
TODO

### iOS app
TODO

## License
This tutorial by [MakeZurich.ch](http://makezurich.ch/) is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).

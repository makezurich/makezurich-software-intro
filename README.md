# #MakeZurich software intro
Introduction to software and platforms available at [#MakeZurich](http://makezurich.ch/).

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
> Crash course: [LoRaWAN and TTN](https://makezurich.ch/#workshop-lorawan), March 23, 7pm at the Smart City Lab Zürich.

The TTN LoRaWAN backend provides access to data sent by your devices, here's a [system overview](https://www.thethingsnetwork.org/docs/).

To send data, [sign up for a TTN account](https://account.thethingsnetwork.org/register), open the [EU](https://console.thethingsnetwork.org/) or [Swiss console](https://console.ttn.opennetworkinfrastructure.org/), create an app and add your device.

The TTN LoRaWAN backend provides [integrations](https://www.thethingsnetwork.org/docs/applications/integrations.html) with 3rd-party services, an [MQTT API](https://www.thethingsnetwork.org/docs/applications/mqtt/api.html) and an [HTTP API](https://www.thethingsnetwork.org/docs/applications/http/).

### Reading your data from TTN with MQTT
The TTN LoRaWAN backend is also an [MQTT broker](https://www.thethingsnetwork.org/docs/applications/mqtt/api.html).

This means you can read your data with any MQTT client library, e.g. for [Go](https://www.thethingsnetwork.org/docs/applications/golang/), [Java](https://www.thethingsnetwork.org/docs/applications/java/), [Node.js](https://www.thethingsnetwork.org/docs/applications/nodejs/) or [Python](https://www.thethingsnetwork.org/docs/applications/python/).

To get uplink packets from a device:

```
$ mqtt sub -t "<AppID>/devices/<DevID>/up" \
-h "eu.thethings.network" -u "<AppID>" \
-P "<AppAccessKey>" # see TTN console, apps
```

To send a packet downlink, Base64 encoded:

```
$ mqtt pub -t "<AppID>/devices/<DevID>/down" \
-m '{"port":1,"payload_raw":"<Bytes>"}' -h …
```

### Reading your data from TTN with HTTP
The TTN LoRaWAN backend offers a Webhook based [HTTP integration](https://www.thethingsnetwork.org/docs/applications/http/).

### Hosting on virtual machines
To host your backend during #MakeZurich, get a free Linux virtual machine (VM) from [Datacenter Light](https://datacenterlight.ch/).

Contact [support@ungleich.ch](mailto:support@ungleich.ch) with the subject *MakeZurich VM* and specify what you need:

CPU cores (1..8), RAM size (1..16) GB, SSD size (10..50) GB and native IPv4 (yes/no).

## 3rd-party services
3rd-party services allow to store or display data, and add logic "in the cloud".

### Dweet.io
[Dweet.io](http://dweet.io/) is a simple storage service for name/value pairs.

* Host: dweet.io
* Port: 443
* POST /dweet/for/THING_NAME?NAME=VALUE
* POST /dweet/for/THING_NAME?NAME=VALUE&NAME2=VALUE2
* GET /get/latest/dweet/for/THING_NAME
* GET /get/dweets/for/THING_NAME

### IFTTT
[IFTTT](https://ifttt.com/) is a rule-based service to integrate connected products.

* https://ifttt.com/maker_webhooks

### Node-RED
[Node-RED](https://nodered.org) is a flow-based development tool for visual programming.

* Host: LOCAL_IP (e.g. on your Laptop or a Raspberry Pi)
* Port: 1880
* https://nodered.org/docs/
* https://cookbook.nodered.org/ (e.g. [mqtt](https://cookbook.nodered.org/mqtt/) or [http](https://cookbook.nodered.org/http/))
* https://www.npmjs.com/package/node-red-contrib-ttn

### ThingSpeak
[ThingSpeak](https://thingspeak.com/) is an IoT platform to store and display sensor data.

* https://www.mathworks.com/help/thingspeak
* Host: api.thingspeak.com
* Port: 80 or 443
* POST /update?api_key=WRITE_API_KEY&field1=42
* POST /update?api_key=WRITE_API_KEY&field1=7&created_at=2019-05-03T00:00:00Z
* GET /channels/CHANNEL_ID/feed.json?api_key=READ_API_KEY 

## Client

### Web app
TODO

### Android app 
TODO

### iOS app
TODO

## License
This tutorial by [MakeZurich.ch](http://makezurich.ch/) is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).

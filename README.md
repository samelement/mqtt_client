# mqtt_client
[![Build Status](https://github.com/shamblett/mqtt_client/actions/workflows/ci.yml/badge.svg)](https://github.com/shamblett/mqtt_client/actions/workflows/ci.yml)
[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2Fshamblett%2Fmqtt_client.svg?type=shield)](https://app.fossa.io/projects/git%2Bgithub.com%2Fshamblett%2Fmqtt_client?ref=badge_shield)

A server and browser based MQTT client for Dart.

The client is an MQTT v3(3.1 and 3.1.1) implementation(an equivalent MQTT v5 client can be found [here](https://pub.dev/packages/mqtt5_client)) supporting subscription/publishing at all QOS levels,
keep alive and synchronous connection. The client is designed to take as much MQTT protocol work
off the user as possible, connection protocol is handled automatically as are the message exchanges needed
to support the different QOS levels and the keep alive mechanism. This allows the user to concentrate on
publishing/subscribing and not the details of MQTT itself.

Examples of usage can be found in the examples directory.  An example is also provided
showing how to use the client to connect to the mqtt-bridge of Google's IoT-Core suite. This demonstrates
how to use secure connections and switch MQTT protocols. The test directory also contains standalone runnable scripts demonstrating subscription, publishing and topic filtering.

The server client supports both normal and secure TCP connections and secure(wss) and non-secure(ws) websocket connections.
The browser client supports only secure(wss) and non-secure(ws) websocket connections.

The client has been used successfully with the MQTT brokers from several of the major cloud providers IOT/MQTT
platforms, including :-
* Google IOT Core
* Amazon AWS
* Microsoft Azure
* IBM

It has also been used with a range of both publicly available brokers such as Mosquitto and proprietary ones.
An example using the adafruit MQTT broker for flutter can be found [here](https://github.com/BitKnitting/flutter_adafruit_mqtt).

The code is originally a port from the C# [nMQTT](https://www.openhub.net/p/nMQTT) client library to Dart.

Please read the changelog for details related to specific versions.

## Installation
If you are using the client in a flutter environment on Android or iOS devices then the following device permission settings are necessary.

### iOS
Add the following keys to your **Info.plist** file, located in **ios/Runner/Info.plist**:
```
<key>NSLocalNetworkUsageDescription</key>
<string>Looking for local tcp Bonjour service</string>
<key>NSBonjourServices</key>
<array>
  <string>mqtt.tcp</string>
</array>
```
### Android
Add the following Android permissions to the **AndroidManifest.xml** file, located in **android/app/src/main/AndroidManifest.xml**:
```
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```
## License
[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2Fshamblett%2Fmqtt_client.svg?type=large)](https://app.fossa.io/projects/git%2Bgithub.com%2Fshamblett%2Fmqtt_client?ref=badge_large)

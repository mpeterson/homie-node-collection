# Homie Node Collection

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Build Status](https://travis-ci.org/luebbe/homie-node-collection.svg?branch=master)](https://travis-ci.org/luebbe/homie-node-collection)

Collection of nodes and examples for Homie. The nodes are designed as independend classes, so they can work standalone. For instance you can easily wire up a firmware for a Sonoff Relay by combining a ButtonNode with a RelayNode.

The software is based on [Homie (v2.0)](https://github.com/marvinroger/homie-esp8266)

## ButtonNode
A pushbutton that just detects a single button press. An optional callback can be triggered by the button press event. The button press is *not* reported back via MQTT. ToDo: detect multiple button presses and report them back.

## ContactNode
A contact that reports its open state (true|false) via MQTT. An optional callback can be triggered by the state change event.

## RelayNode
A relay that can be set on (true|false) via MQTT message. An optional LED GPIO pin can be passed in the constructor. This pin will be set high/low synchronous to the relay.

## BME280Node
A node for a Bosch BME280 I2C temperature/humidity/pressure sensor. Reports the three values back via MQTT.
Advertises the values as:
* homie/\<device-id\>/\<sensor-name\>/temperature
* homie/\<device-id\>/\<sensor-name\>/humidity
* homie/\<device-id\>/\<sensor-name\>/pressure

The units are advertised as subtopics:
* homie/\<device-id\>/\<sensor-name\>/temperature/unit
* homie/\<device-id\>/\<sensor-name\>/humidity/unit
* homie/\<device-id\>/\<sensor-name\>/pressure/unit

## DHT22Node
A node for a DHT22 temperature/humidity sensor. Reports the two values back via MQTT.
Advertises the values as:
* homie/\<device-id\>/\<sensor-name\>/temperature
* homie/\<device-id\>/\<sensor-name\>/humidity

The units are advertised as subtopics:
* homie/\<device-id\>/\<sensor-name\>/temperature/unit
* homie/\<device-id\>/\<sensor-name\>/humidity/unit


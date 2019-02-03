# node-red-mqtt-example

## Usage

1. git clone this repo
2. cd to the root of the local copy
3. run: `npm start`
4. browse to http://localhost:1880
5. build a flow using the pre-built mqtt components,
6. connect to mmqt as mosquitto (two t's) on port 1883

## Flow suggestion

1. Use the inject node wired to mqtt input to trigger messages
2. Use the debug node to log mqtt output messages.

## Cleanup

1. Ctrl-C in terminal window
2. `docker-compose down` - will remove the containers and images

* * *

## Example

### How to use the examples

1. Copy the JSON of each example to the clipboard
- From the node-red menu: __Import / Clipboard__
* Paste the clipboard JSON into the dialog box
* Click the __new flow__ tab
* Click __Import__
* Click __Deploy__
* Click the __debug__ (bug) icon in the panel on the right

Most examples can be triggered by click the button (left) tab on the inject nodes.

### simple mqtt

```
[{"id":"7042507f.0ab0b","type":"tab","label":"simple mqtt","disabled":false,"info":"# A simple mqqt example \n\nClick a button (inject) node to publish a time stamp message through mqqt."},{"id":"741c6c55.0d1bd4","type":"mqtt in","z":"7042507f.0ab0b","name":"","topic":"button/1","qos":"0","broker":"f5279b01.b328d8","x":120,"y":160,"wires":[["cf9f3773.2f3578"]]},{"id":"cf9f3773.2f3578","type":"debug","z":"7042507f.0ab0b","name":"","active":true,"tosidebar":true,"console":false,"tostatus":false,"complete":"payload","x":290,"y":160,"wires":[]},{"id":"a7192ce2.ef2cb","type":"mqtt out","z":"7042507f.0ab0b","name":"","topic":"button/1","qos":"0","retain":"false","broker":"f5279b01.b328d8","x":290,"y":100,"wires":[]},{"id":"9321eaae.4175f8","type":"inject","z":"7042507f.0ab0b","name":"","topic":"","payload":"","payloadType":"date","repeat":"","crontab":"","once":false,"onceDelay":0.1,"x":120,"y":100,"wires":[["a7192ce2.ef2cb"]]},{"id":"f5279b01.b328d8","type":"mqtt-broker","z":"","name":"","broker":"mosquitto","port":"1883","clientid":"","usetls":false,"compatmode":true,"keepalive":"60","cleansession":true,"birthTopic":"","birthQos":"0","birthPayload":"","closeTopic":"","closeQos":"0","closePayload":"","willTopic":"","willQos":"0","willPayload":""}]
```
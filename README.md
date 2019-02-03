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
2. From the node-red menu: __Import / Clipboard__
3. Paste the clipboard JSON into the dialog box
4. Click the __new flow__ tab
5. Click __Import__
6. Click __Deploy__
7. Click the __debug__ (bug) icon in the panel on the right

Most examples can be triggered by clicking the button (left) tab on the inject nodes.

### simple mqtt

```
[{"id":"7042507f.0ab0b","type":"tab","label":"simple mqtt","disabled":false,"info":"# A simple mqtt example \n\nClick a button (inject) node to publish a time stamp message through mqtt."},{"id":"741c6c55.0d1bd4","type":"mqtt in","z":"7042507f.0ab0b","name":"","topic":"button/1","qos":"0","broker":"f5279b01.b328d8","x":120,"y":160,"wires":[["cf9f3773.2f3578"]]},{"id":"cf9f3773.2f3578","type":"debug","z":"7042507f.0ab0b","name":"","active":true,"tosidebar":true,"console":false,"tostatus":false,"complete":"payload","x":290,"y":160,"wires":[]},{"id":"a7192ce2.ef2cb","type":"mqtt out","z":"7042507f.0ab0b","name":"","topic":"button/1","qos":"0","retain":"false","broker":"f5279b01.b328d8","x":290,"y":100,"wires":[]},{"id":"9321eaae.4175f8","type":"inject","z":"7042507f.0ab0b","name":"","topic":"","payload":"","payloadType":"date","repeat":"","crontab":"","once":false,"onceDelay":0.1,"x":120,"y":100,"wires":[["a7192ce2.ef2cb"]]},{"id":"f5279b01.b328d8","type":"mqtt-broker","z":"","name":"","broker":"mosquitto","port":"1883","clientid":"","usetls":false,"compatmode":true,"keepalive":"60","cleansession":true,"birthTopic":"","birthQos":"0","birthPayload":"","closeTopic":"","closeQos":"0","closePayload":"","willTopic":"","willQos":"0","willPayload":""}]
```

### mult in / one out mqtt

```
[{"id":"278077ea.760cd8","type":"tab","label":"multi in / one out mqtt","disabled":false,"info":"# A multiple input / one output mqtt example \n\nClick either button to publish a string message through mqtt.\n\nThe topic on the mqtt output node is left blank. \nIt will pass along the topics that are set in the inject nodes.\n\nThe mqtt input node uses a wild card (button/#) topic to process messages for either node."},{"id":"6b4821c8.3604e","type":"mqtt in","z":"278077ea.760cd8","name":"","topic":"button/#","qos":"0","broker":"f5279b01.b328d8","x":100,"y":240,"wires":[["3eb8fdf6.915c92"]]},{"id":"3eb8fdf6.915c92","type":"debug","z":"278077ea.760cd8","name":"","active":true,"tosidebar":true,"console":false,"tostatus":false,"complete":"payload","x":310,"y":240,"wires":[]},{"id":"784fb45c.06357c","type":"mqtt out","z":"278077ea.760cd8","name":"mqtt output","topic":"","qos":"0","retain":"false","broker":"f5279b01.b328d8","x":330,"y":120,"wires":[]},{"id":"2f0226d4.bb960a","type":"inject","z":"278077ea.760cd8","name":"button alpha","topic":"button/alpha","payload":"alpha","payloadType":"str","repeat":"","crontab":"","once":false,"onceDelay":0.1,"x":110,"y":100,"wires":[["784fb45c.06357c"]]},{"id":"c07f0b44.34e328","type":"inject","z":"278077ea.760cd8","name":"button beta","topic":"button/beta","payload":"beta","payloadType":"str","repeat":"","crontab":"","once":false,"onceDelay":0.1,"x":110,"y":160,"wires":[["784fb45c.06357c"]]},{"id":"f5279b01.b328d8","type":"mqtt-broker","z":"","name":"","broker":"mosquitto","port":"1883","clientid":"","usetls":false,"compatmode":true,"keepalive":"60","cleansession":true,"birthTopic":"","birthQos":"0","birthPayload":"","closeTopic":"","closeQos":"0","closePayload":"","willTopic":"","willQos":"0","willPayload":""}]
```


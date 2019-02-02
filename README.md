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
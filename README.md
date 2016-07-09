MQTTClientPlugin
================

MQTT Client Cordova Plugin for iOS. It uses an Objective-C native MQTT Framework [https://github.com/ckrey/MQTT-Client-Framework] for MQTT connections

Install
-------
`cordova plugin add https://github.com/rbackhouse/MQTTClientPlugin.git`

Usage
-----

All the possible configuration options

```
var mqttConfig = {
	clientId: "", 
	tls: true, // Use a tls connection
	certfile: "", // Specify a p12 formatted certfile that can be found in the cordova.file.dataDirectory
	certpath: "", // Alternately, specify a full path to a p12 formated certfile
	certpwd: "",
	username: "",
	password: "",
	keepalive: 30,
	clean: true,
	will: {
		topic: "",
		payload: "",
		qos: 1,
		retain: true
	}
};
```

Create a connection

`var device = mqttclient.connect(host, port, mqttConfig);`

Add event listeners for connect, close, error and message events

```

device.on("connect", function() {
	....
});

device.on("close", function() {
	....
});

device.on("error", function(err) {
	....
});

device.on("message" function(topic, message) {
	....
});

```

Publish a message to a topic

`device.publish(topic, message, {qos: 1, retain: true});`

Subscribe to a topic

`device.subscribe(topic, {qos: 1});`

Unsubscribe from a topic

`device.unsubscribe(topic);`

Close the connection

`device.end();`

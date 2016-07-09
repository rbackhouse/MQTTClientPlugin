MQTTClientPlugin
================

MQTT Client Cordova Plugin for iOS. It uses an Objective-C native MQTT Framework [https://github.com/ckrey/MQTT-Client-Framework] for MQTT connections

Install
-------
`cordova plugin add https://github.com/rbackhouse/MQTTClientPlugin.git'

Usage
-----

```
var mqttConfig = {
	clientId: "",
	tls: true,
	certfile: "",
	certpath: "",
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

var device = mqttclient.connect(host, port, mqttConfig);

device.on("connect", function() {
});
device.on("close", function() {
});
device.on("error", function(err) {	
});
device.on("message" function(topic, message) {
});

device.publish(topic, message, {qos: 1});

device.end();
```
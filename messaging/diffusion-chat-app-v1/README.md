# diffusion-chat-app-v1

This is sample chat application using [Diffusion](https://www.pushtechnology.com/product-overview) Cloud.
Users can chat in realtime across various meeting rooms.
A simple projects, illustrating production and consumption of messages to and from a Diffusion Cloud instance.

# Lesson 1

**diffusion-chat-app-v1** introduces de concept of Publish and Subscribe to [topics (data structures)](https://docs.pushtechnology.com/docs/6.5.1/manual/html/introduction/overview/topics_data.html).

# APIs used in this application

* [diffusion.connect](https://docs.pushtechnology.com/docs/6.5.1/js/globals.html#connect) > [*create your host*](https://management.ad.diffusion.cloud/)
```js
diffusion.connect({
	host : host, // Use your Diffusion service or connect to our sandbox "diffusionchatapp.eu.diffusion.cloud"
	principal : "user",
	credentials : "password"})
```
* [session.topics.add](https://docs.pushtechnology.com/docs/6.5.1/js/interfaces/topiccontrol.html#add)
```js
session.topics.add(_roomTopic, diffusion.topics.TopicType.JSON);
```
* [session.addStream](https://docs.pushtechnology.com/docs/6.5.1/js/interfaces/session.html#addstream)
```js
session.addStream(_roomTopic, diffusion.datatypes.json());
```
* [session.select](https://docs.pushtechnology.com/docs/6.5.1/js/interfaces/session.html#select)
```js
session.select(_roomTopic);
```
* [session.topicUpdate.set](https://docs.pushtechnology.com/docs/6.5.1/js/interfaces/topicupdate.html#set)
```js
session.topicUpdate.set(_roomTopic, diffusion.datatypes.json(),
	{
		text: msg,
		name: name,
		timestamp: new Date().toLocaleTimeString()
	});
```

# Requirements

*  Download our code examples or clone them to your local environment:
```
 git clone https://github.com/pushtechnology/tutorials/
```
* A Diffusion service (Cloud or On-Premise), version 6.5.0 or greater.
* Create a service [here](https://management.ad.diffusion.cloud/).
* Follow our [Quick Start Guide](https://docs.pushtechnology.com/quickstart/#diffusion-cloud-quick-start) and get your service up in a minute!

# Setup

Set lines 44-46 of `public/js/app.js` to the hostname of your Diffusion Cloud service, which you can find in your service dashboard.
You can also leave the default values and connect to our sandbox service:
* host: host ("diffusionchatapp.eu.diffusion.cloud" by default)
* user: 'user'
* password: 'password'

# Execution

Really easy, just open the index.html file locally and off you go!

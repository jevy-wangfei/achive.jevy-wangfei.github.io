---
layout: default
title: Design a system? Not a easy work
category: timeline
tags: portfolio
quote: Week 8, Design a system? Not a easy work
---

Because I am the only one who worked as software engineer at enterprise, I take the responsibility of designing the system. It is a online ordering and delivery system, and it seams very easy to handle. But when I step into the detail, more and more tough jobs are waiting me to solve.

System structure design
I make two assumptions before the system structure designing:

1. Support ten thousand restaurants in future.
2. At lease one hundred dishes in a restaurant. And the size of each dish photo is about 0.5MB.
3. There are system access peak at moon and 5:00pm to 7:00pm of lunch and dinner.
4. Flow and convenient usage to view restaurants, dishes in photos and text.
5. System will be extended and undertake more function, such as sharing delicious food by taking photos.
6. Multi devices.
7. Multi client.

Based on those assumptions, following design features should be considered:

1. At least 50GB volume for pictures storage is required.
2. At least 1,000 concurrent service accessing in peak time supports.
3. Web explorer, iOS devices, Android devices and Tablet Devices support.

<img style="background:#FFF" src="./img/tmp/SystemArchitecture0.1.png"/>

Because it is a business system, reliable, stable, response time and extendable features are considered. Solutions show as bellow:

1. At least 50GB volume for pictures storage is required.
2. At least 1,000 concurrent service accessing in peak time supports.
3. Web explorer, iOS devices, Android devices and Tablet Devices support.
4. Caching data on server to provide quick response time and good quality of services.
5. Using mongo DB to manage pictures.
6. Using MySQL to manage restaurants, dishes, orders and payment etc data.
7. Using RESTful API to provides data accessing from clients.
8. Using rich clients application to handle customers operation.

API and application design
Based on the structure introduced above, we build a web host server, MySQL database and  program restaurants and dishes CRUD APIs. Pictures are stored on server current, we will transfer the pictures storage to mongo DB in next stage.

The system provides four main distinctive services:
	Group delivery, hot dishes suggestion and find food by location

In project meeting, we talked a lot  services. However, how to implement them using code? We abstract models and actions from the services, define the API of to operate data on remote server and define the operation on client applications.

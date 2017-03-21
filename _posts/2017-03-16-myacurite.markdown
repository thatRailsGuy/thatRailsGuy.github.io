---
layout:     post
title:      "My AcuRite"
subtitle:   "My experience working on a consumer facing API"
date:       2017-03-16 14:38:00
author:     "Clint Cecil"
header-img: "img/10-yellowstone-river.jpg"
---

Once OneVue launched, the team shifted to work on [My AcuRite](https://www.myacurite.com). My AcuRite is a site dedicated to home environmental monitoring using devices manufactured by Chaney Electronics under the AcuRite brand. Sensor types include temperature, humidity, wind speed and direction, rainfall, lightning proximity, light intensity, and water detection. The site offers monitoring that will notify users when sensors go out of range, useful for things like detecting freezing around pipes or the presence of water in a basement.

"Smart Hubs" are paired with each sensor and connected to the internet to send data to the servers. These hubs send sensor data to our servers a few times per minute. This presents an interesting challenge in scalability as we are processing approximately four hundred thousand requests per hour. Micro-services handle the load by scaling independently to process data, relying on queueing systems to keep everything cohesive.

Most of the existing framework built for OneVue was applicable for My AcuRite. Most of the work done has been optimization and support for more custom endpoints to limit data transmission on mobile devices. We created a second bastion API which allows access to some of the same micro-services behind OneVue. We also now support native apps on iOS and Android.

One other challenge in building the site was the migration of data from the old site. We worked with the old contractors to spec out an API to access customer data, then built a webpage that allowed users to enter username and password and import the data to the new site. This also triggered a flag to update the firmware of their devices to point at the new service. Once the firmware was updated, it started reporting data and would be automatically claimed by the "new" user in our system. We tested the system by sending invites to a few thousand users as beta testers and monitored the performance of our system.

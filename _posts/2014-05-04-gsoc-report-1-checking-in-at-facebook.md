---
title: "GSoC Report 1: Checking-in at Facebook with Gjs"
tags: gsoc gsoc2014 gnome
---

Ladies and gentlemen, this is my first GSoC progress report, I hope you enjoy it. As you should remember, my GSoC project aims to **integrate GNOME Maps with Facebook and Foursquare**. Technically speaking, the project consists in the following modification in GNOME.

- Add a new **Feature** called Check-In to GNOME Online Accounts (GOA) (in the vocabulary of GOA, a feature is something like Chat, Photos, Printers, Files, etc.)
- Add the Check-In feature to the Facebook backend.
- Implements the Foursquare backend with the Check-In feature.
- Implements some sort of libraries that holds the API calls logic (there is actually one for Facebook called `libgfbraph`). Actually, maybe this is not going to be part of the GSoC project for the moment and the logic would be implemented in GNOME Maps source code, but in the future, this should be changed!
- Add the Check-In related features to GNOME Maps

During the last weeks, I deeply entered to the GOA and Gjs world, my goals for that period was to implement the two first items mentioned above (that is, finish the Facebook backend modifications) and then implements some example scripts that performs Check-In using the Online Accounts configured in the system, plus, some code to be reused GNOME Maps should start to be crafted at this point.

## What was done?

### Facebook backend modification

The first thing that I did was to implements the modifications to the Facebook GOA backend. Since this backend is already implemented, this task was relatively easy but it helped me a lot to better understand technologies like D-Bus and GObject C programming.

The result? roughly, this fully functional switch (inside the red rectangle) :P

![GOA Check-in switch]({{ site.baseurl }}/images/goa-check-in.png)

You can check this progress at [my GOA development repository](https://github.com/eagleoneraptor/gnome-online-accounts), `wip-checkin` branch.

### Two example scripts

There are also two example scripts that shows how to perform a Check-In, those scripts only use the Facebook backend since as of today the Foursquare backend is not implemented. One of the scripts, called `listFacebookPlaces.js` just lists Facebook Places Pages information from geo coordinates and distance parameters, this is necessary since Facebook needs a Place Page ID to associate a user post to a location. The other script, called `performCheckIn.js` performs a Check-In in Facebook using the message and place passed by parameter.

Both examples uses common code (basically `checkIn.js`) that will be candidate to be part of GNOME Maps codebase

You can check those and future examples in [this repository](https://github.com/eagleoneraptor/goa-checkin-examples)

## What's next?

I think that the next step is to enter to the Foursquare world and its API. The first thing to do is to implement the Foursquare backend in GOA and then, write the examples, as I did with Facebook. This also will help us to understand the particularities of each service so we can design a better GUI to the users of those services. For example, when a was working with the Facebook examples, I had no idea beforehand that I was going to need a list of Facebook Places to get a Place ID, this give us a clue of the existance of a Combo Box or something like that in the future GUI design to allow user to select the place to Check-In, something that would not have imagined beforehand. I expect that something similar will happen with Foursquare.

Stay tuned for more reports!

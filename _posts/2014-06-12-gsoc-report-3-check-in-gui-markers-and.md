---
title: "GSoC Report 3: Check-In GUI, markers and bubbles"
tags: gsoc gsoc2014 gnome
---

First of all, sorry for the delay of this report, I was a little busy with non-GSoC stuff. Now I'm back, ready for code and make GNOME better!

In my [previous report]({{ site.baseurl }}{% post_url 2014-05-16-gsoc-report-2-foursquare-in-gnome %}) I told you that I was hopping to have some screenshots for the Check-In GUI that is going to be present in GNOME Maps 3.14, if you got excited after read that (because you got excited, right!!??), you are on luck, I have your screenshots :)

Let's start!

## What was done?

### Check-In GUI for GNOME Maps

Let's start with some screenshots

![GNOME Maps Check-in first step]({{ site.baseurl }}/images/checkin-1.png)

![GNOME Maps Check-in second step]({{ site.baseurl }}/images/checkin-2.png)

![GNOME Maps Check-in third step]({{ site.baseurl }}/images/checkin-3.png)

If you remember my previous report, I told you the idea of how Check-In is going to work, this is the result. The first and second step are susceptible to don't appear at all. For the first step, if you use just one account for Maps, this step is ommited. For the second step, if we can find the selected POI for check-in in the social service database, we also omit this step, if not, we give a list of found places so the user can select the appropiate place to check-in. The second step emergence depends too much on how similar is Overpass API POI compared to the social network POI (mainly name and nearness)

We discussed with Zeeshan, Andreas and Mattias about using directly the social network API as a POI provider for Maps. This actually will solve the problem of the 2nd Check-In step, but we will keep it simple for 3.14 and discuss if we can do it for a next iteration

In the 3rd step there is a *More options* expander, this shows options for the check-in like visibility (for Foursquare and Facebook) and Facebook/Twitter broadcasting (only for Foursquare).

You cannot use this dialog directly at this moment because I need some of the [Rishi](http://www.rrsj.org) code to get it working (when you click a POI in Maps, a bubble will be shown with the "Check-In" button on it).

You can get more information in [Bugzilla ticket \#731113](https://bugzilla.gnome.org/show_bug.cgi?id=731113).

### New markers and bubbles

Do you remember how current user position marker and bubble looks? Well, it looks like this

![GNOME Maps old user location marker]({{ site.baseurl }}/images/user-location-marker-old.png)

Now, I'm refactoring the markers and bubbles code to use `GtkPopover` based bubbles

![GNOME Maps new user location marker]({{ site.baseurl }}/images/user-location-marker-new.png)

*Please note that I'm not lost in the middle of the Sahara Desert, this is just an example :)*

Actually, this is not the final appereance of the marker, this is work in progress. We will add some buttons in the bubble to perform some actions related to the location. GNOME designers had crafted [some mockups](https://github.com/gnome-design-team/gnome-mockups/blob/master/maps/v2/markers-and-bubbles.png) some time ago related to the markers and bubbles

Also, I only ported the current user location marker, others markers present in Maps need to be refactored as well.

You can get more information in [Bugzilla ticket \#722871](https://bugzilla.gnome.org/show_bug.cgi?id=722871).

### Some progress in GOA Foursquare provider

Now we have an official GNOME application in Foursquare and the review of the GOA Foursquare provider is happening.

You can get more information in [Bugzilla ticket \#729837](https://bugzilla.gnome.org/show_bug.cgi?id=729837).

## What's next?

While I wait for more reviews from Gnomers, I'm going to make more progress in the new markers and bubbles, adding the missing new markers and helping Dario and Rishi to port their respective markers to the new code.

If you have any suggestion or criticism on the current progress, this is perfect moment to speak! :D

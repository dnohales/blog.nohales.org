---
title: "GSoC Report 4: Stalking your friends with GNOME"
tags: gsoc gsoc2014 gnome
---

More than one month without a GSoC report? Luckily my mentors are so kind to get angry with me ;) . The truth is that I was really busy getting ready for some final exams, but that stuff is finished and I am really motivated to continue.

## What was done?

### Stalking your friend with GNOME

I started to like the word *stalk* since I started to play GTA V and got known about the Lifeinvader in-game social network, now this word is coming to GNOME Maps. I was working in a feature to display check-ins from user friends and from the user him/herself. This feature is going to be available only for Foursquare users that have a Foursquare account configured in GNOME Online Accounts. Since I was mostly working in the non-GUI part of the feature I don't have much to show you, just one screenshot:

![GNOME Maps friends check-in]({{ site.baseurl }}/images/friendscheckin.png)

*No! I'm not using maximize and minimize buttons in my environment! that's happening to me with the latest version of Gtk+, dunno why :)*

These are markers that Maps will show to represent a check-in (for the current user or for the user itself), obviously, if you press on that marker, a bubble with more information about the check-in will appear, I'm working with [Andreas](https://plus.google.com/u/0/107646837068615384568) to get a nice mockup for that bubble. *Maybe some GNOMErs remember me asking for help in IRC to get a photo with a circle shape, that was what I was trying to do :) .*

Maybe you want to get involved in this feature since a have some usability worries that I explain in [this Bugzilla comment](https://bugzilla.gnome.org/show_bug.cgi?id=732509#c2), any feedback related to this will be appreciated.

### Reviews, reviews and more reviews

Now I'm starting to getting some nice feedback from Dario and Rishi (GSoC students working on Maps) about the [markers and bubbles I'm coding](https://bugzilla.gnome.org/show_bug.cgi?id=722871).

I hope when everything get merged, we will have a really nice maps app for GNOME.

## What's next?

Showing check-ins in Maps is the last goal for my GSoC project, so the next tasks is to finish this and work hard to get everything merged before 3.14.

## GUADEC

Sadly, I am not going to be in Strasbourg this weekend, not because I couldn't get sponsorship, but due personal stuff. I hope next year to be different, because I really wanted to be there, hacking with you :(

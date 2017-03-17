---
title: "GSoC Final Report: Tying up loose ends"
tags: gsoc gsoc2014 gnome
---

So this is the end of the second most exciting project I ever made after the SDL pong game I made when I started to learn programming (those youth projects were welding in my heart, they are hard to overcome 😄). And of course that doesn't mean that this is the end of my GNOME contributions, hopefully I graduate this year and I won't be eligible to GSoC next year but that doesn't mean that my contributions will stop here, moreover with the pending tasks that I already have for 3.16.

GNOME Maps received a lot of love this year, three students including myself was working hard to add some neat features to Maps. Sadly, not everything of this work will be able to 3.14. We actually needed to request a feature freeze exception to include some of GSoC features:

- [Markers and bubbles](https://bugzilla.gnome.org/show_bug.cgi?id=722871)
- [Via points](https://bugzilla.gnome.org/show_bug.cgi?id=731068)

Actually, the Via points feature was merged while I was writing this post :), we worked hard together with Jonas and Dario these last days to get this feature pushed.

The GSoC features may not be present in 3.14 are:

- [Points of Interest](https://bugzilla.gnome.org/show_bug.cgi?id=731587), Rishi afforded some technical difficulties during the development of this feature, he needed to make a big refactorization these last days on the POI caching code, you can get more information in this [Rishi's post](http://www.rrsj.org/2014/09/02/GSoC-and-GUADEC/).
- [GNOME Online Accounts Foursquare provider](https://bugzilla.gnome.org/show_bug.cgi?id=729837), is very sad to not get this merged this in time because it was in a very pushable state, but *The Three Stooges Syndrome* affected my communication with GNOME members to create the GNOME app in Foursquare, and that delayed the merging.
- [Check-In feature in Maps](https://bugzilla.gnome.org/show_bug.cgi?id=731113), this one was very pushable too, maybe some nits to be solved, also, the delay in the Foursquare provider inclusion affected the inclusion of this feature.
- [Friends check-ins](https://bugzilla.gnome.org/show_bug.cgi?id=732509), this one wasn't completed, I dare to say that is 60% completed, some discussion with designers must happen to continue with this.

We hope to have everything mentioned and more for 3.16!

## Thank you!

I want to thank to Google and GNOME for give the opportunity to get involved into this wonderful project, it was a really nice experience and I learned a lot. Thanks a lot to GNOME members involved in this project: Jonas Danielsson, Mattias Bengtsson, Zeeshan Ali, Andreas Nilsson. Special thanks to Jonas for his unbreakable patience during the review of my code and constant involvement. Thanks to my GSoC partners: Dario and Rishi, for the inspiring effort they put in their projects and the good willing to work together.

***Thank you all!***

---
title: "GSoC Report 2: Foursquare in GNOME"
tags: gsoc gsoc2014 gnome
---

I know, I know, you just can not wait to read another wonderful post from this blog (sorry, bad joke). Either way, here I am, with another GSoC 2014 progress report.

If you have read my [previous post]({{ site.baseurl }}{% post_url 2014-05-04-gsoc-report-1-checking-in-at-facebook %}), you'll remember that the next step for this project is to start working with the Foursquare API to implement its backend in GNOME Online Accounts and then, code some examples to perform check-ins in Foursquare.

## What was done?

### New Foursquare backend in GNOME Online Accounts

![GOA Foursquare account selection]({{ site.baseurl }}/images/goa-foursquare-account-select.png)

![GOA Foursquare login webview]({{ site.baseurl }}/images/goa-foursquare-webview.png)

![GOA Foursquare account]({{ site.baseurl }}/images/goa-foursquare-account.png)

As you can see, we have now the Foursquare backend working in GNOME Online Accounts. Fortunately and unexpectedly for me (since I am a ignorant in GObject in C and even more in Autotools), was relatively easy, through existent backend codebase like Facebook and Pocket backends.

This progress is in review process at GNOME Bugzilla and I hope this should be part of GNOME in a matter of days. You can check the [ticket \#729847](https://bugzilla.gnome.org/show_bug.cgi?id=729837) to get more information.

### Foursquare Check-In examples

A lot of progress has been made in the check-in code examples, now the code is more service-agnostic and the service-specific code is well separated. During the development of these examples, I've been able to get a more suitable code to be used directly in GNOME Maps

As I hope you remember, this code is available [here](https://github.com/eagleoneraptor/goa-checkin-examples).

### Check-In GUI Discussion

Mattias Bengtsson, Andreas Nilsson and I were discussing at IRC about the future GUI in GNOME Maps, we benefit a lot from this discussion since there were certain aspects of social services that should be taken into account during the design.

Broadly, the Check-In will work as follows:

1. User selects a Point Of Interest (POI) or maybe his/her current location in the Map.
2. A popover shows with information about POI, a "Check-In" button is showed in that popover
3. User press the button
4. An account selector dialog is showed so the user can select the account under which to perform the check-in. If the user has only one account, this dialog is ommited.
5. Based on the POI information, Maps search a related place page in the social service (Facebook or Foursquare) so we can perform the check-in in that place.
6. If the social service return to us results with ambiguity (i.e. the POI has more than one related page in Facebook), a place selector dialog is showed so the user can select the correct place. If there is not ambiguity, that dialog is ommited
7. A dialog is showed to inform the user where he/she is going to perform the check-in and with which account, and also a text entry to associate a message to the check-in. We don't have discussed this yet, but maybe we can add some check-in privacy configuration or other extra options.

### Hacking `libgfbgraph`

During the development of the example code, I've detected some issues in the `libgfbgraph` library (the glib based library to use Facebook API) related to the OAuth2 Access Token handling. Basically, the library does not use the Access Token provided by GOA, so the applications are forced to reload the Access Token at startup regardless of whether or not the token is expired.

I've discussed this with the library author, Álvaro Peña and we agreed that this must be changed.

## What's next?

The next step is to start to code the Check-In GUI that will be used in Maps, so I hope to show you some screenshots for the next report :) .

Stay tuned!

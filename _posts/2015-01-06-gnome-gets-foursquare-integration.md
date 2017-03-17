---
title: GNOME gets Foursquare integration
tags: gnome
---

If you were reading my GSoC 2014 reports, you surely remember that I was working on integrating GNOME Maps with social networks, so you can share the place you are in Facebook and Foursquare (and Twitter if you enable an option in Maps!). This surely is not going to be an everyday feature, but I learned a lot during its development (and during the whole GSoC).

In my [last GSoC report]({{ site.baseurl }}{% post_url 2014-09-03-gsoc-final-report-tying-up-loose-ends %}) I told you that I hope to have this feature for GNOME 3.16, fortunately it got merged in upstream a couple of weeks ago. The work consist of two parts:

- GNOME Online Accounts (GOA) Foursquare provider: this allow users to link his/her Foursquare account to the system by using GNOME Control Center. Applications and libraries then get the account information through GOA API (that works internally using D-Bus to contact GOA daemon).
- Check-in feature for GNOME Maps: this uses the configured Facebook and Foursquare online accounts to post check-ins in the respective streams.

If you have geolocation support in GNOME and press the marker that represents your current location or press the upper left button in Maps while you have a Facebook or Foursquare account configured, you'll see a *Check in* button in the bubble that appears on the map view. Press it and follow the steps. I hope we find other ways to access this feature, right now is pretty much hidden (hey, everybody love hidden features!).

![GNOME Maps check-in button]({{ site.baseurl }}/images/check-in-button-final.png)

## Using Foursquare account in your application

One thing that it's still pending to implement is a basic native GObject based library to use the Foursquare API and to get easily access to GOA account like what [libgfbgraph](https://wiki.gnome.org/Projects/GFBGraph) does with Facebook. Anyway, it's a really easy thing to do even without a library to help you.

The idea is simple: GOA only provides you authentication information about the account, depending on the case, this information could be a username, password, access token, etc. With that information, you can do whatever you want, meaning, use it to make API calls to a web service or send it to the NSA.

Once you get the Foursquare account object (a [GoaObject](https://developer.gnome.org/goa/stable/GoaObject.html) instance) by using the [GoaClient](https://developer.gnome.org/goa/stable/GoaClient.html) API you need to extract the access token for the account by using [goa_oauth2_based_call_get_access_token](https://developer.gnome.org/goa/stable/GoaOAuth2Based.html#goa-oauth2-based-call-get-access-token) and generate the URL for the Foursquare API call, something like:

```
https://api.foursquare.com/v2/{call_name}?
    {call_parameters}&
    v={api_version}&
    oauth_token={goa_token}
```

For instance:

```
https://api.foursquare.com/v2/checkins/add?
    shout=The%20check-in%20message&
    venueId=4567&
    v=20140226&
    oauth_token=OI5435O43H25OI432HU5IOU234H52U
```

I recommend you to use [librest](https://wiki.gnome.org/Projects/Librest) to perform the API calls.

You can learn more by checking out the GNOME Maps code, specially `src/foursquareGoaAuthorizer.js`, `src/serviceBackend.js` and `src/foursquareBackend.js` files.

Cheers!

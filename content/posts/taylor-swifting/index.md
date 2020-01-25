---
title: 'Taylor Swifting'
date: Sun, 30 Nov 2014 06:28:36 +0000
draft: false
tags: ['Blog', 'Coding', 'LastFM', 'Music', 'Web']
---

I had a [really random idea](https://twitter.com/shiruken/status/536957959503241217) the other day for a simple coding project using the LastFM API: When was the last time you listened to Taylor Swift? This is obviously an extremely important statistic to know for the Taylor Swift obsessed. I already made a tool to [lookup the first time you listened to an artist](/first) using your LastFM profile, so this was a relatively straightforward adaptation. I also wanted to take this opportunity to leverage the power of [jQuery](http://jquery.com/) to asynchronously load the information rather than simply waiting for a static page. Check out [The Last Swifting](/swifting) page or continue reading for more information.

![Screenshot of The Last Swifting result page](screenshot.jpg)

I use [`jQuery.ajax()`](http://api.jquery.com/jquery.ajax/) to asynchronously GET information from a server-side PHP script using the input LastFM username. As with the existing [user + artist lookup page]({{< relref "lastfm-first-listen" >}} "LastFM First Listen"), the [`user.getArtistTracks`](http://www.last.fm/api/show/user.getArtistTracks) was our desired API method. This returns a list of tracks by a given artist scrobbled by the user in reverse chronological order. Since we only care about the most recent Taylor Swift listen, we can use the `&limit=1` parameter to reduce the number of results returned. Some simple XML DOM traversal gives us all the information we need: track name, timestamp (UTC), and album artwork url. This data is parsed by the client-side Javascript and presented as seen above. Since Javascript is handling the conversion of Unix timestamp to human readable format, the client timezone is properly displayed.

During development of the webpage, I wanted to make the username input more interesting than just a plain textbox. I had the idea of making the field expand automatically as more text was entered, which seemed trivial since I was already using jQuery. This turned out to be more difficult than anticipated since simply reading the size of the text and adjusting the input size would often result in extra trailing space. The animation also appeared extremely choppy and was often unreliable. I eventually stumbled upon [this StackOverflow post](http://stackoverflow.com/questions/8100770/auto-scaling-inputtype-text-to-width-of-value/22423199#22423199) that offered a beautiful solution. It does a better job of calculating the width of the current text and smooths animations using the CSS transition parameter. This allowed me to directly integrate the username into the results text without worrying about glaring extra space.

![Text Entry Demonstration](text.gif)

**Check It Out:** [**The Last Swifting**](/swifting)


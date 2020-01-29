---
title: 'LastFM First Listen'
date: Tue, 26 Mar 2013 03:55:01 +0000
draft: false
tags: ['Coding', 'Web', 'Music', 'LastFM']
---

When was the first time you listened to M83? What about LIGHTS? If you're a [LastFM](http://www.last.fm/) user, then I've made a [little web-app](/first) you can use to look it up! All you need is an active LastFM account and to have been tracking your music listening with their scrobbling service.

![First Time I Listened to M83](M83First.jpg)

All you need to do is enter any LastFM username and artist and then hit submit. The website uses the LastFM `user.getArtistTracks` API method to fetch every single track the user has scrobbled from that particular artist. The XML returned file is segmented into 50 plays-per-page but fortunately reports the total number of pages in the first child element. This number is used to jump to the last page of the data, which contains the very first scrobbled track by the user for the particular artist. From there it's just a matter of parsing the XML structure and grabbing the necessary information for display on the webpage with PHP.

**Check It Out**: [**First LastFM Listen**](/first)
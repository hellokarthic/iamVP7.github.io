---
title:  "Exploring Notifications WebExtension API"
date:   2016-08-08 02:20:00
description: Notifications API
categories: addons
tags: [addons,firefox]
---

In this post we will be exploring more about Notifications API for Firefox WebExtensions. In last post I was writing about [Getting Started with WebExtension]({{ site.url/2016/02/Lets-Get-Started-With-WebExtensions/}}). Just read it before starting, so you can config your browser accordingly. 

There are lot of time, we love notifications, say when a new message comes to whatsapp, new Post is written in the blogs and so on. These notifications are really great features both in web and mobile which will help us to save lot of time. Firefox Webextensions have one of the amazing API to create notifications, you can find more detail in the [Mozilla Developer Network](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/API/Notifications), some of the aspects of this API will be discussed below.

**Creating Simple Notification**
================================

>
>	 chrome.notifications.create( "vp7",{
>    
>	"type": "basic",
>    
>	"iconUrl": chrome.extension.getURL("icons/chillout-32.png"),
>    
>	"title": "Alert message",
>    
>	"message": "Time to drink water"
>  
>	});


In the above example *vp7* is the notification id, and the remaining part is the options for that notification.

Generally Notification id is not mandatory it is optional, but it is good practice to give, so we can identify and easily update next time.

![Notification Simple]({{ site.url }}/assets/notification_simple.png)

In the options part we are having different parameters which will be defining the Notification. First one is *type* of the notification, currently Firefox (Firefox 48) is supporting only basic type, but we also have image, list and progress as types.

We can compare with the above image and understand the Simple notification easily, the **Bold Letters -- Alert message** is the title of the notification, and the normal font face "Time to drink water" is the message of the notification. And in the left side you can see the small notification icon for this particular notification, usually company logos goes here.

**Creating Image Notification**
===============================
We all know, the WebExtensions is universal extensions, without changing any code I tried the same extension in the Google Chrome, just to check whether I can test image Notifications.


>
> 	chrome.notifications.create( "vp7",{
> 
>       "type": "image",
> 
>       "iconUrl": chrome.extension.getURL("icons/chillout-32.png"),
> 	
>	"imageUrl": chrome.extension.getURL("icons/chillout-32.png"),
>
>       "title": "Alert message",
> 
>       "message": "Time to drink water"
> 
>       });


It was very easy to test the Image notifications, we can use it in blogs generally, so we can drive traffic to other post. Take a look at the below image, you can clearly understand how useful it will be to use Image notifications in your blog.

The two main changes that have been introduced here is **"type": "image",** and additionally **"imageUrl": chrome.extension.getURL("icons/chillout-32.png")** 


![Notification Image]({{ site.url }}/assets/notification_image.png)



In the upcoming posts we can discuss other two Notification types and also the different event listerners, clearing and updating the notifications and so on.

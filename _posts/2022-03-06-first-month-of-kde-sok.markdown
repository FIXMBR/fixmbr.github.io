---
layout: post
title: "First month of KDE SoK 2022"
date: 2022-03-06 21:00:00 +0100
categories: kde sok
---

Hello, This is my first blogpost for KDE SoK 2022.

## What I'm working on.

My work centres around alerts in KDE Connect iOS app. As it's under development, a lot of information is communicated to the user using system alerts. iOS is limited to displaying only one alert at a time and doesn't have any native system for queuing them.

Sample Alert:

![example alert]({{ site.url }}/assets/alert.jpg){: height="500" }

## Progress

During last month I learned a lot about swift. Getting familiar with the code took me a while.

I started by implementing a basic alert queue. After consulting it with my Mentors, I got the data types right.
{% highlight swift %}
struct AlertContent{
let title: LocalizedStringKey
let content: Text?
let buttons: () -> AlertActionBuilder.Buttons
}
{% endhighlight %}

Buttons also got me stuck as they are created using a custom iOS 14 compatibility view. But eventually, I wrapped my head around this too.

Before my changes, every message was a separate alert. Now there is a single alert with content that changes dynamically.

{% highlight swift %}
.alert(alertManager.currentAlert.title,isPresented: alertsBind,
actions: alertManager.currentAlert.buttons){
alertManager.currentAlert.content
}
{% endhighlight %}

It uses a custom binding `alertsBind` that detects when the alert is dismissed and, if available, pushes the next alert in.

Overall I spent some time figuring out some of swift's quirks. It differs from languages that I'm more familiar with, like Python / JS / C++.

The result can be seen here - queued alerts being shown one after another.

![example alert]({{ site.url }}/assets/alerts.gif)

## Next steps

- Switch alerts in app to use this new system.
- Clean up the code

You can see my current progress in the [merge request](https://invent.kde.org/network/kdeconnect-ios/-/merge_requests/42) I created.

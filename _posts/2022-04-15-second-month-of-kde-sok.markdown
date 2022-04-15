---
layout: post
title: "Second month of KDE SoK 2022"
date: 2022-04-15 21:00:00 +0100
categories: kde sok
---

Within SoK 2022 project, I worked on an in-app alert queueing system for KDE Connect iOS

Since my [previous blog post](https://fixmbr.github.io/kde/sok/2022/03/06/first-month-of-kde-sok.html) I've been working on migrating all alerts to the new system, iOS 14 support and modernization of manual IP input screen.

## Migrating to the new system

Alerts in the app are now using the new system. Everything has been migrated and works well (everything, besides one text alert, which I will discuss later in the post).


## iOS 14 compatibility

There were some issues with queuing working on iOS 14, as iOS 15 introduced a lot of new features in swift. One of the problems was caused by a compatibility layer that allowed one view to have multiple `.alert()` modifiers. As of now, there is in fact only one alert in the entire app, so removing the compatibility layer was an obvious solution.

Here is a screen from iOS 14 with working alerts.

![ios14 alerts]({{ site.url }}/assets/ios14.png){: height="500" }


## Configure Devices by IP screen

One of the reasons behins changing the "Configure Devices By IP" screen was to bring it up to modern apple standards. This screen used an outdated alert with text input, which is now gone. In the current version, the entire list of IPs is editable and you can add a new line with a click of a button. It works on the same basis as the native iOS reminders app.

Here is a before and after.

![ip view screen]({{ site.url }}/assets/ipview.png){: height="500" }

The other reason was that the text alert isn't supported by the new alert manager :)

## Other things

Having done all of that I focused on cleaning up the code and adding documentation for the new system.

## Closing thoughts

My work for SoK is done. It has been a great opportunity to learn more about iOS development and work with a community-driven open source project. Over the span of the last few months, Swift really grew on me. With the help of my mentors' work
was going smoothly, and SoK was the thing I needed to finally contribute to the Open Source community.

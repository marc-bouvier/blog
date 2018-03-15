---
layout: post
date: 2018-03-15
title: "How to reconnect websocket and subscriptions"
tags: vueJs vueX websocket reconnection
published: false
---

## Context

In an application like [the chat we made previously](https://marc-bouvier.github.io/2018/02/15/chat-vuejs-rocket-chat/), 
I need to be able to resume websocket connection when it is closed unexpectedly. I also need to subscribe back to channels
and notification I was previously subscribed to.

## Problem

When a device goes offline of sleeping, the websocket connection can be lost and subscriptions can also be lost.

## A way to do it

### Wrap events

### Store significant events of websocket state

We need to store some specific events when we try to reconstruct websocket connection. We don't want to replay all events 
(especially business events). 

During the lifecycle of the application we will first **connect to the websocket**, then **authenticate to the API** through it. 
Later, we will **subscribe to channels** (rooms) and notifications.

So I identified types of events

* connected : connected to websocket
* anthenticated : authenticated to API
* subscribedToRoomMessages : listening messages from a specific room
* subscribedToNotifyRoomTyping: listening to /typing event from a specific room

### Replay events sequentially

### 

## Resources

* 

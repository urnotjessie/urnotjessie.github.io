---
layout: post
title:      "Understanding Redux"
date:       2018-12-24 18:44:32 +0000
permalink:  understanding_redux
---


### Redux in plain English

![Imgur](https://i.imgur.com/KleaOJC.png)



**Action Creator:**

A function that is going to create or return a plain JavaScript object

**Action:**
* A plain JavaScript object that describes the changes we want to make to the data in the application
* An action has * type* and *payload* properties, * type* describes the changes we want to make in out data,* payload* describes the context around the change we want to make

**Dispatch:**

Dispatch takes an action, make copies of the object and passes off to different places in the application

**Reducers:**

A function that takes in an action and update the data based on the *type* of the action, and then return it so it can be centralized in some other location

**State:**

A central repository of all information created by Reducers which helps React app to easily access all the data intstead of going around to each individual Reducer




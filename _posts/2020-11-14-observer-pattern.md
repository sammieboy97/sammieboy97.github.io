---
title: "Observer Pattern"
date: 2020-11-14
categories:
  - Design Pattern
tags:
  - Refactoring
  - OOPS
  - LLD
---

> Hey Subject, I would like to register myself to your subscribers list. Please update me too when your state changes. Thank you.
> <cite> Observer class </cite>

----

This is a continuation of the software design pattern series.

----

<h3> Observer pattern </h3>
  Ever been in a situation where if one object's state changes, you need some other objects to change their behavior and state too? Then, Observer pattern is your weapon from the armory.

----

<h4>Ok. So how to solve? </h4>
  Publishers + Subscribers = Observer Pattern. <br>
  If you understand newspaper subscriptions, you pretty much understand the Observer Pattern, only we call the publisher the SUBJECT and the subscribers the OBSERVERS. <br> <br>
  In Software design it goes like <br>
  **Publisher:** The object which is to be watched. <br>
  **Subscriber:** The object which needs to be reflected when a publisher's state changes. <br>
  Here the publishers and subscribers are loosely coupled thus making them work independently and they don't need to know each other exclusively.

---

  **Example 1:**
    You have a set of data and whenever it is updated, you need to update the grid display, graph display, third party display and so on.

  **Example 2:**
    A photo is posted in your social network and all the respective person's followers should be getting a notification.
    
---

<h4> Cool. So how to actually implement it? </h4>
In Observer pattern, 4 different components gets involved excluding the Client.
<ul>
  <li> Subject interface/abstract class </li>
  <li> Concrete Subject  </li>
  <li> Observer interface</li>
  <li> Concrete Observer </li>
</ul>

<h4> -> Subject interface </h4>
  This abstract class or interface has the methods for registering and de-registering of observers.
<h4> -> Concrete Subject class </h4>
  The class which implements the Subject interface. This maintains the state of the Subject object and takes care of notifying all its observers by calling their update() method.
<h4> -> Observer interface </h4>
  The interface which all the observers need to implement. This has the update() method which the implementing classes have to implement.
<h4> -> Concrete Observer </h4>
  The class implementing the Observer interface. This has their own implementation of the update() method which will be triggered by the observer.

---

<h3> Design Structure </h3>
  ![image tooltip here](/assets/images/observer-patter-structure.svg)

  photo courtesy: [link](https://en.wikipedia.org/wiki/Observer_pattern#/media/File:Observer_w_update.svg)

---

<h3> Sample code </h3>

<script src="https://gist.github.com/SamuelJohnson01997/f4397fa682977a26d51d8acdcf3a450b.js"></script>

  
As seen in the code example when DataStore's setData is called from client, all the observers of the DataStore subject are getting notified and their respective update() method is called.
Thus when observer's state changes, all the subscribed observers are getting informed.

---

Thank you. Hope this helps. Looking forward to more learning and sharing. Cheers :)

----

<h3> Stay connected: </h3>

# <i class="fab fa-fw fa-twitter-square"></i> Connect on [Twitter](https://twitter.com/sammieboy97)
# <i class="fab fa-fw fa-linkedin"></i> Connect on [Linkedin](https://www.linkedin.com/in/samuel-johnson-r/)

----

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/

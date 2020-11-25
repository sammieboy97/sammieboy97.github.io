---
title: "Abstract factory design Pattern"
date: 2020-11-25
categories:
  - Design Pattern
tags:
  - Refactoring
  - OOPS
  - LLD
---

> Please take this interface for creating families or dependant objects without specifying their concrete classes.
> <cite> Abstract factory design pattern </cite>

----

This is a continuation of the software design pattern series.
You can checkout the previous posts from [my-blog](https://www.buildwithsammie.com)

----

<h3> Abstract factory design pattern </h3>
  In Abstract factory design pattern, the family of different Products can be grouped together and be instantiated without the client specifying the concrete class.  <br>
  <h4> How it is different from Simple Factory pattern? </h4>
  In this pattern, just like the Products implement from the Product interface, all the types of Products will be grouped together in different concrete Factories which will be implementing a factory interface. The  client will be using the Factory interface without caring what implementation it is. <br>

----

<h4>Cool. So how to implement Abstract Factory design pattern? </h4>
In Abstract Factory design pattern, four main component gets involved excluding the Client.
<ul>
  <li> Product Interfaces </li>
  <li> Concrete Product implementations </li>
  <li> Factory Interface </li>
  <li> Concrete Factory implementations </li>
</ul>

---

<h4> -> ProductInterface </h4>
  The interface which all the products that can be instantiated should be implementing. Example: Meat
<h4> -> Concrete Product implementation</h4>
  The different Concrete classes implementing the different Product interfaces. Example: WesternStyleMeat, IndianStyleMeat
<h4> -> Factory Interface </h4>
  The interface which should be implemented by all the factories which is trying to create/group a family of Products.
<h4> -> Concrete Factory implementations </h4>
  The Concrete classes for each different family groups which should be implementing the factory interface.
  
---

Let's take example related to Pizzzza itself. Why? Cuz I personally love them.

Ok, to keep it simple lets take the ingredients of Pizza. 
Some of the most important ones are
<ul>
  <li> Cheese </li>
  <li> Meat </li>
</ul>

Consider there are Western type of ingredients and as well as Indian. So it's kinda two different family of ingredients.

Consider the Western type includes ingredients like
<ul>
  <li> WesternStyleCheese </li>
  <li> WesternStyleMeat </li>
</ul>
and the Indian type includes
<ul>
  <li> IndianStyleCheese </li>
  <li> IndianStyleMeat </li>
</ul>
<br>
So we could group them to two different factories. Check the sample code.

<h3> Design Structure </h3>
  ![image tooltip here](/assets/images/abstract-factory-design-pattern.gif)

  photo courtesy: [link](https://www.dofactory.com/img/diagrams/net/abstract.gif)

---

<h3> Sample Code </h3>

<script src="https://gist.github.com/SamuelJohnson01997/0b619da42ef283810407e61f5da39b67.js"></script>

We can now group all the different family of products together and keep on extending to more families too. Thanks to abstract factory design pattern for that ;) <br>

----

Ps: Special Thanks to <a target="_blank" href="https://www.amazon.in/gp/product/B07FVRS9QN/ref=as_li_tl?ie=UTF8&camp=3638&creative=24630&creativeASIN=B07FVRS9QN&linkCode=as2&tag=samiemovic-21&linkId=57e26cfb293ea3ab6b47aaa98f03ad5f">Head First Design Patterns</a><img src="//ir-in.amazon-adsystem.com/e/ir?t=samiemovic-21&l=am2&o=31&a=B07FVRS9QN" width="1" height="1" border="0" alt="" style="border:none !important; margin:0px !important;" />

----

Thank you. Hope this helps. Looking forward to more learning and sharing. Cheers :) <br>
Connect, share and text me about your views. We can have some discussion :)

----

<h3> Stay connected: </h3>
Subscribe: <a href="https://feedburner.google.com/fb/a/mailverify?uri=BuildWithSammie&loc=en_US">Subscribe to Build with Sammie feed for newsletter by Email</a>

# <i class="fab fa-fw fa-twitter-square"></i> Connect on [Twitter](https://twitter.com/sammieboy97)
# <i class="fab fa-fw fa-linkedin"></i> Connect on [Linkedin](https://www.linkedin.com/in/samuel-johnson-r/)

----

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/

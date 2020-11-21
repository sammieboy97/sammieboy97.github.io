---
title: "Factory method Pattern"
date: 2020-11-18
categories:
  - Design Pattern
tags:
  - Refactoring
  - OOPS
  - LLD
---

> Let the subclass decide which class to instantiate. 
> <cite> Factory method Pattern </cite>

----

This is a continuation of the software design pattern series.
You can checkout the previous posts from [my-blog](https://www.buildwithsammie.com)

----

<h3> Factory method pattern </h3>
  In factory method, the subclass will be the one deciding which class to instantiate.  <br>
  <h4> What do you mean and how it is different from Simple Factory pattern? </h4>
  In this pattern, no external factory interface(responsible for creating objects) will be passed to the class like in Simple Factory pattern. <br>
  Here, it provides an interface for creating products/objects in a super class but allows the subclasses to alter the type of products/objects to be created.

----

Take the example we saw in Simple Factory pattern in the previous post. Pizzzza <3
Ref: [link](https://www.buildwithsammie.com/design%20pattern/simple-factory-pattern/)

Now imagine what if we want to Localize the Pizza store like ChennaiPizzaStore, PunjabPizzaStore, ... How does the code needs to be changed? <br> Note: It should be changed in such a way that even if N number of such stores come, the code should be extendable. 

<h4> Interesting. What can be done? </h4>

Instead of having an explicit factory interface for creating the product, we can extend the PizzaStore and let the subclasses create their own style of Pizzas. <br>
This is the crux of factory method pattern as the definition says <b> "Define an interface for creating an object, but let subclasses decide which class to instantiate. The Factory method lets a class defer instantiation it uses to subclasses" </b>

<h4>Cool. So how to implement Factory method pattern? </h4>
In Factory method pattern, four main component gets involved excluding the Client.
<ul>
  <li> Product Interface (Pizza) </li>
  <li> Concrete Product implementations (ChennaiStyleCheesePizza) </li>
  <li> Abstract Creator class </li>
  <li> Concrete Creator class </li>
</ul>

---

<h4> -> ProductInterface </h4>
  The interface which all the products that can be instantiated should be implementing.
<h4> -> Concrete Product implementation </h4>
  The Concrete classes implementing the Product interface. Example: ChennaiStyleCheesePizza, MumbaiStyleCheesePizze
<h4> -> Abstract Creator class </h4>
  The abstract class which has the abstract method (factory method) for creating the Products which needs to be Overridden by the Child classes and create the respective Product objects.
<h4> -> Concrete Creator subclass </h4>
  The subclass extending the Creator Abstract class overriding the abstract create method (factory method) and having it's own implementation of instantiating the Product classes.
  
---

<h3> Design Structure </h3>
  ![image tooltip here](/assets/images/Factory_Method_Design_Pattern_UML.jpg)

  photo courtesy: [link](https://upload.wikimedia.org/wikipedia/commons/4/43/W3sDesign_Factory_Method_Design_Pattern_UML.jpg)

---

<h3> Sample Code </h3>

<script src="https://gist.github.com/SamuelJohnson01997/5fc0b68e2c146577cf152985cebc4be8.js"></script>

We can see each PizzaStore(s) can have their own Pizza types and could instantiate the Pizza types available with them. Thus we could localize the PizzaStores. <br>
More PizzaStores could be added extending the abstract PizzaStore class and it works on it's own too. <br>
No coupling == More Extendable. Change my mind.

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

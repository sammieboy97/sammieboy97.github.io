---
title: "Simple Factory Pattern"
date: 2020-11-18
categories:
  - Design Pattern
tags:
  - Refactoring
  - OOPS
  - LLD
---

> Don't just instantiate a concrete class and use it straight away. You'll be regretting in the longer term
> <cite> Simple Factory Pattern </cite>

----

This is a continuation of the software design pattern series.
You can checkout the previous posts from [my-blog](https://www.buildwithsammie.com)

----

<h3> Simple factory pattern </h3>
  Ever been in a situation where when you need to change the declaration of a concrete class and you got to change in all the locations across your code base? <br>
  Ever faced a situation where your client and concrete classes are coupled together so that when you try to introduce a similar concrete class and replace the old one, it gets harder? <br>
  Then you got to start programming to the interface/super-class instead of the implementation/sub-class. This can be achieved by introducing a factory for creating such implementations.

----

<h4>Ok. So how does it actually work? </h4>
  Let's take an example of ordering a Pizza. The software takes type of the pizza and input and gets the respective pizza as output. <br>
  Consider there are two types of pizzas.
  <ul>
    <li> Pepperoni Pizza </li>
    <li> Cheese Pizza </li>
  </ul>

  Our typical code without factory pattern looks like this. <br>

  <script src="https://gist.github.com/SamuelJohnson01997/76a87c69e76c17b1877e625551139149.js"></script>


Now we could see that the orderPizza method is tightly coupled with the creation of concrete Pizza classes and whenever a new pizza type like PastaPizza gets introduced, the orderPizza method gets really messy as it's dealing directly with which concrete class in instantiated. It's probably time to encapsulate it. <br>
Check the following code. <br>
<script src="https://gist.github.com/SamuelJohnson01997/502b09fe1042fc364981d978890f31b9.js"></script>


Now the complete responsibility of creation of the concrete Pizza classes are given to the PizzaFactory and it will be the single point of contact of instantiating those Pizza classes. 

----

<h4> Cool. So give me a gist to implement Simple factory pattern? </h4>
In Simple factory pattern, just three main component gets involved excluding the Client.
<ul>
  <li> Product Interface (Pizza) </li>
  <li> Concrete Product implementations (Cheese Pizza) </li>
  <li> Simple Factory implementation (SimplePizzaFactory) </li>
</ul>

<h4> -> ProductInterface </h4>
  The interface which all the products the factory can create should be implementing. 
<h4> -> Concrete Product implementation </h4>
  The Concrete classes implementing the Product interface. There are the classes which are needed to be instantiated from the factory.
<h4> -> Simple Factory class </h4>
  The main responsibility of this class is to get the args and depending on it, create the needed the product and return to the calling method.

---

<h3> Design Structure </h3>
  ![image tooltip here](/assets/images/simple-factory-structure.gif)

  photo courtesy: [link](https://sites.google.com/site/haithamraik/Home/design-pattern-list/simple-factory/simplefactorystructure11.gif?attredirects=0)

---

  
In the coming posts, I will explain the variants of the factory patterns which will eliminate the limitations in the simple factory pattern. 

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

---
title: "Singleton Pattern"
date: 2020-11-16
categories:
  - Design Pattern
tags:
  - Refactoring
  - OOPS
  - LLD
---

> Hey. You can't initialize me, but you can get the only one instance of myself which is shared across your app by asking my static sub-routine. I can help you with what I can.
> <cite> Singleton class </cite>

----

This is a continuation of the software design pattern series.
You can checkout the previous posts from [my-blog](https://www.buildwithsammie.com)

----

<h3> Singleton pattern </h3>
  Ever been in a situation where you just need to restrict initiation of a class and also wanted to ensure that only one instance of the class should be present in the JVM at a given time? Then Singleton pattern is your way to go.
  
----

<h4> Disclaimer </h4>
  I'd be honest here. 
  Singleton pattern is dangerous. Use it only if it is really needed. It even breaks the Single responsibility principle from SOLID* as here, the same class has two responsibilities including initiation of itself and having it's own behavior as well.

----

<h4>Ok. So where can I use Singleton pattern? </h4>
  One of the good places where I'd say Singleton pattern is a good candidate is in Logging. When logging to a file from your app, it's better to go through a single point of contact which eliminates a lot of complexities.

---

  **Example 1:**
    Logging to a file from your app.

  **Example 2:**
    Reading a configuration file and keeping them in memory in the class for faster access across the app.
    
---

<h4> Cool. So how to implement Singleton pattern? </h4>
In Singleton pattern, just one component gets involved excluding the Client.
<ul>
  <li> SingletonClass </li>
</ul>

<h4> -> SingletonClass </h4>
  The class has the constructor as private, so it cannot be initialized outside the class. <br>
  The class has its own reference with private modifier. <br>
  There are two ways to initialize this reference. <br>
  <ul>
    <li> Initialize during the class loading (ie) when declaring the instance, just add the initializing part too. Check example code 1 </li>
    <li> Initialize during the first time getInstance() method is called from this class. Check example code 2 </li>
  </ul>
  Thread safety needs to be considered while using the singleton pattern as in multi threaded environment, the same object is going to be shared across threads. So handling them properly should be a high priority.

---

<h3> Design Structure </h3>
  ![image tooltip here](/assets/images/singleton-pattern-structure.png)

  photo courtesy: [link](https://en.wikipedia.org/wiki/File:Singleton_UML_class_diagram.svg)

---

<h3> Sample code </h3>
code1: <br>
<script src="https://gist.github.com/SamuelJohnson01997/77fe61673cf9b218f37a1335d4f3b5dd.js"></script>

code2: <br>
<script src="https://gist.github.com/SamuelJohnson01997/8c62fc46dfb203821e0d34f75ad41dd6.js"></script>

  
As seen in the code example, the instance could be get across the application using the getInstance() method and it will guarantee to have just single instance of that class to be alive at a given time.

PS:
  Why Singleton is dangerous. Have a look [link](https://puredanger.github.io/tech.puredanger.com/2007/07/03/pattern-hate-singleton/) <br>
  \* -> More on the SOLID principles in the future.

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

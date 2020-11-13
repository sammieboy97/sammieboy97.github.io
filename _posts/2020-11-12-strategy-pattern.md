---
title: "Strategy Pattern"
date: 2020-11-12T15:34:30-04:00
categories:
  - Design Pattern
tags:
  - Refactoring
  - OOPS
  - LLD
---

> Writing readable and extendable code is magic. Be a magician. 
> <cite> Anonymous (jk. It's me) </cite>

This is going to be a series of blog posts where I'll share various design patterns which we can use to solve our everyday problems in software design.

Okay, so what on earth is a design pattern and why should I know about it? <br>
There are a lot of common repeating problems during software design. We need to use tested, proven development paradigms for solving these. Consider design pattern as a template to solve such problems. This makes development faster and also greatly increases code readability and extensibility.

This might seem overwhelming but we'll take it one pattern at a time starting with some frequently used ones in our daily work.

<h3> Strategy pattern </h3>
  The strategy pattern helps to decide which algorithm to use during runtime thus giving more reusability and extensibilty.

<h4>Problem: </h4>
  You have a problem where you can solve it using different algorithms and you need to choose which one to use depending on the input from the client, you can go for Strategy pattern.
  
  **Example 1:**
    You are giving offers in your ticket booking site based on the current month.

  **Example 2:**
    You are compressing a file and you need to decide the format during runtime.

  **Example 3:**
    You are implementing a login feature for your product and you need to enable login with different service providers like google, facebook, github and so on.

  **Example 4:**
    You are implementing various payment methods like COD, paypal, UPI, etc in your product website.

How it can be solved using Strategy pattern?
In strategy pattern, 3 different components gets involved excluding the Client.
<ul>
  <li> Context class</li>
  <li> Strategy interface </li>
  <li> Different Strategy implementations </li>
</ul>

<h4> -> Context class </h4>
  This class will be the single point of contact to the client. Context class isn't responsible for choosing any strategy, the client chooses them and sets them to the context.  Usually context allows strategy as a constructor or/and a setter method, so runtime can be handled effectively.
<h4> -> Strategy interface </h4>
  The interface which needs to be implemented by all the algorithms which wishes to be interchangable.
<h4> -> Strategy implementation class </h4>
  These classes implement the Strategy interface and they will be interchangable during runtime.

<h3> Design Structure </h3>
  ![image tooltip here](/assets/images/strategy-pattern-structure.png)

  photo courtesy: [link](https://refactoring.guru/images/patterns/diagrams/strategy/structure.png)

<h3> Sample code </h3>

  ```java

import java.util.Scanner;

interface DiscountStrategy {
    public Double getDiscountPercentage();
}

class HolidaysDiscountStrategy implements DiscountStrategy{
    public Double getDiscountPercentage() {
        return 0.4;
    }
}

class NoDiscountStrategy implements DiscountStrategy{
    public Double getDiscountPercentage() {
        return 0.0;
    }
}

class PurchaseStrategyContext { // Context acts as a single point of contact  for the clients.
    Double cost;
    DiscountStrategy discountStrategy;
    public PurchaseStrategyContext(Double cost) {
        this.cost = cost;
        discountStrategy = new NoDiscountStrategy();
    }
    public DiscountStrategy getDiscountStrategy(int monthNumber) {
        if(monthNumber > 10 && monthNumber <=12) {
            return new HolidaysDiscountStrategy();
        } else {
            return new NoDiscountStrategy();
        }
    }
    public void applyDiscountStrategy(DiscountStrategy strategy) {
        this.discountStrategy = strategy;
    }

    public Double getCost() {
        return (this.cost - (this.discountStrategy.getDiscountPercentage() * this.cost));
    }
}

public class StrategyPattern {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter the cost of the cart");
        Double costOfTheCart = sc.nextDouble();
        System.out.println("Enter the current month");
        int currentMonth = sc.nextInt();
        PurchaseStrategyContext context = new PurchaseStrategyContext(costOfTheCart);
        DiscountStrategy strategy = context.getDiscountStrategy(currentMonth); //Get can be done here or strategy can be initialized here
        context.applyDiscountStrategy(strategy);
        Double finalPrice = context.getCost();
        System.out.println("The final cost after the discount is " + finalPrice);
    }
}

  ```

As seen in the code, the respective discount strategies can be set at runtime depending on the client's input. Suppose if we need to add a new discount strategy, we just need to write a class implementing the Strategy interface and that's it. If client set the new strategy to the context, it will work as smooth as butter.

Thank you. Hope this helps. Looking forward to more learnings and sharings. Cheers :)

----

<h3> Stay connected: </h3>

# <i class="fab fa-fw fa-twitter-square"></i> Connect on [Twitter](https://twitter.com/sammieboy97)
# <i class="fab fa-fw fa-linkedin"></i> Connect on [Linkedin](https://www.linkedin.com/in/samuel-johnson-r/)

----

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/

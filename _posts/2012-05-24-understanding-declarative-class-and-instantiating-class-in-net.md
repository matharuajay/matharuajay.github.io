---
toc: false
id: 2671
title: Understanding declarative class and instantiating class in .net
date: 2012-05-24T18:02:48+00:00
author: Ajay Matharu
layout: post
guid: https://www.ajaymatharu.com/?p=2671
permalink: /understanding-declarative-class-and-instantiating-class-in-net/
dsq_thread_id:
  - 702033756
categories:
  - .Net
  - CodeProject
  - OOPS
  - Visual Studio
tags:
  - .Net OOPS
  - 'C#.Net'
  - declarative class
  - declarative class vs instantiating class
  - Inheritance
  - instantiating class
  - OOPS
  - shadowing in .net
---
While creating an object of any class, the class which is on the left of declaration is called Declarative class and one on the right is called Instantiating class.

Taking an hypothetical example, consider the following class diagram,

<div style="width: 288px" class="wp-caption aligncenter">
  <img title="Inheritance" src="https://www.ajaymatharu.com/wp-content/uploads/2012/05/inheritance.png" alt="Inheritance" width="278" height="352" />
  
  <p class="wp-caption-text">
    Man inheriting from Emotions
  </p>
</div>

<pre name="code" class="c-sharp">public class Emotions
    {
        public void Laugh()
        {
            Console.WriteLine("Laughing");
        }

        public void Cry()
        {
            Console.WriteLine("Crying");
        }
    }

    public class Man : Emotions
    {
        public void Read()
        {
            Console.WriteLine("Man Reads");
        }

        public void Play()
        {
            Console.WriteLine("Man Plays Cricket");
        }
    }</pre>

For the above class when we create object like this,

<pre class="c-sharp">Emotions e = new Man();</pre>

The above object &#8220;e&#8221; shows following intellisense ,

<div style="width: 379px" class="wp-caption aligncenter">
  <img title="Void Main" src="https://www.ajaymatharu.com/wp-content/uploads/2012/05/VoidMain.png" alt="Void Main" width="369" height="241" />
  
  <p class="wp-caption-text">
    Void Main
  </p>
</div>

e.{will list public functions from Declarative (Emotions) class but will execute from Instantiating (Man) class}

So, in such scenarios (inheritance), when we declare object of base class and instantiate from derived class, objects show public functions, properties and variables of base (declarative) class in intellisense. However if any of those function is overridden, then derived (instantiating) class function is executed.

The above rule does not stand in shadowing. As in shadowing child class shadows the function from base class. So base class is unaware of any such function declaration.  In that scenario base (declarative) class function will be executed.

&nbsp;

&nbsp;

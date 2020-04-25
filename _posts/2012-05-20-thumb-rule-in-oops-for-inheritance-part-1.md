---
toc: false
id: 2674
title: 'Thumb rule in OOPS for Inheritance &#8211; Part 1'
date: 2012-05-20T17:00:36+00:00
author: Ajay Matharu
layout: post
guid: http://www.ajaymatharu.com/?p=2674
permalink: /thumb-rule-in-oops-for-inheritance-part-1/
dsq_thread_id:
  - 697286181
categories:
  - .Net
  - CodeProject
  - OOPS
  - Visual Studio
tags:
  - Law of inheritance
  - Law of polymorphism
  - Loosely coupled system
  - rule of inheritance
  - Thumb rule of inheritance
  - Thumb rule of oops for inheritance
  - Tightly coupled system
---
Lets look at the very important rule in OOPS for inheritance.

> _**&#8220;Wherever object of parent class is expected object of child class can go.&#8221;**_

**Where this can be used?**

This rule is used to design loosely coupled system. So that we can optimize the code, thereby improving the system. Consider the following system,

<div id="attachment_2678" style="width: 696px" class="wp-caption aligncenter">
  <a href="http://www.ajaymatharu.com/thumb-rule-in-oops-for-inheritance-part-1/tightlycoupledsystem/" rel="attachment wp-att-2678"><img class="size-full wp-image-2678" title="TightlyCoupledSystem" src="http://www.ajaymatharu.com/wp-content/uploads/2012/05/TightlyCoupledSystem.png" alt="TightlyCoupledSystem" width="686" height="183" srcset="http://www.ajaymatharu.com/wp-content/uploads/2012/05/TightlyCoupledSystem-300x80.png 300w, http://www.ajaymatharu.com/wp-content/uploads/2012/05/TightlyCoupledSystem.png 686w" sizes="(max-width: 686px) 100vw, 686px" /></a>
  
  <p class="wp-caption-text">
    Tightly Coupled System
  </p>
</div>

The above system has a common function PrintCheque() which is tightly coupled with specific type. PrintCheque() does the same thing for all three classes but still it is defined in each class and takes specific type as parameter. This makes the system tightly coupled to the specific type.

&nbsp;

**Problem:**

Although the function does same thing it is defined in all three classes and takes parameter of specific type making it bound to that type. Also in future if we add another type, we have to redefine this function which will take object of that new type as parameter.

&nbsp;

**Solution**

We declare a new class called Employee and inherit these classes from employee class.

<div id="attachment_2679" style="width: 696px" class="wp-caption aligncenter">
  <a href="http://www.ajaymatharu.com/thumb-rule-in-oops-for-inheritance-part-1/looselycoupledsystem/" rel="attachment wp-att-2679"><img class="size-full wp-image-2679" title="LooselyCoupledSystem" src="http://www.ajaymatharu.com/wp-content/uploads/2012/05/LooselyCoupledSystem.png" alt="LooselyCoupledSystem" width="686" height="361" /></a>
  
  <p class="wp-caption-text">
    Loosely Coupled System
  </p>
</div>

The above designed system is loosely coupled. You can see that the PrintCheque() function now takes parameter of type Employee, so any class that inherits from Employee can be passed as parameter. Also any new type added, when inherited from Employee class, will be able to call this function. Thus making our system loosely coupled system.

&nbsp;

**Source Code:**

Employee Class

<pre name="code" class="c-sharp">abstract class Employee
    {
       private string _name;
       private double _salary;

       public Employee(string mname, double mamt)
       {
           _name = mname;
           _salary = mamt;
       }

       public string Name {
           get
           {
               return _name;
           }
       }

       public double Salary
       {
           get {
               return _salary;
           }
       }

       public abstract double NetSalary();

       public static void PrintCheque(Employee temp)
       {
           Console.WriteLine("Name={0} Salary={1}", temp.Name, temp.NetSalary());
       }

    }</pre>

&nbsp;

Manager Class

<pre name="code" class="c-sharp">class Manager:Employee
    {
        private double _taxes = 0.25;

        public Manager(string mname, double mamt)
            : base(mname, mamt)
        { }

        public override double NetSalary()
        {
            return Salary * (1 - _taxes);
        }

        public void PlanProjects()
        {
            Console.WriteLine("Manager plans projects");
        }
    }</pre>

&nbsp;

Analyst Class

<pre name="code" class="c-sharp">class Analyst:Employee
    {
        double _taxes = 0.20;
        double _compoff = 0.10;

        public Analyst(string mname, double mamt)
            : base(mname, mamt)
        {
        }

        public override double NetSalary()
        {
            return Salary * (1 - _taxes + _compoff);
        }

        public void DesignSystems()
        {
            Console.WriteLine("Analyst designs systems");
        }
    }</pre>

&nbsp;

SalesMan Class

<pre class="c-sharp" name="code">class SalesMan:Employee
    {
        double _comm = 0.05;

        public SalesMan(string mname, double mamt) : base(mname, mamt) { }

        public override double NetSalary()
        {
            return Salary * (1 + _comm);
        }

        public void Markets()
        {
            Console.WriteLine("Salesman sells");
        }
    }</pre>

&nbsp;

Main

<pre class="c-sharp" name="code">class Program
    {
        static void Main(string[] args)
        {
            Manager emp1 = new Manager("abc", 700000);
            Analyst emp2 = new Analyst("pqr", 500000);
            SalesMan emp3 = new SalesMan("lmn", 200000);

            Employee.PrintCheque(emp1);
            Employee.PrintCheque(emp2);
            Employee.PrintCheque(emp3);

        }

        //inheritance is not always used for relationships 
        //in this case inheritance is used to exploit law of polymorphism
        //by making the system loosely bound so that we dont have to
        //write PrintCheque() function again and again for each type of employee

        //law of polymorphism says 
        //whereever object of parent class is expected object of child class can go
        //so we designed the printcheque function such that it can be used for any
        //child class of employee class making it loosely coupled system.

    }</pre>

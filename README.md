#Inheritance vs. Composition

So you've built a program in which you have a `Person` class. You also have an `Employee` class. And a `Customer` class. Both inherit from `Person`. But what happens when a given `Person` is an `Employee` who wants to buy something with their `employeeDiscount`? Wouldn't they be a `Customer` then, who can engage in a `Transaction` with the `Company`?

Alternatively, consider the following:

We have a farm simulator in which we have `Tractor` to harvest carrots. We also have a `Person` who works on the farm. The `Person` harvests carrots that the `Tractor` misses. Just because both the `Tractor` and the `Person` both can harvest carrots, should the `Tractor` inherit from the `Person` class (or vice-versa)?

##Multiple inheritance

So in our first scenario, we want to instantiate an object with the behaviors of both an `Employee` AND a `Customer`. With inheritance, we are limited, certainly in Objective-C, to picking a single super class. But with composition, we use categories to extend a class with as many behaviors as we might like. A `Person` can be extended with the behavior of `Employee` and the behavior of `Customer`.

##Has-A vs. Is-A

In our second example, we are very clearly presented a scenario in which composition makes more sense. Harvesting is an extension of both `Person` and `Tractor`. Both a `Tractor` and a `Person` can do much more than `harvest`, and the remainder of their behaviors (aka methods) are quite different. This is a good signal that we should use categories instead of inheritance. If, on the other hand, we had an instance which had all of the behaviors and properties of another class, we might start to consider one the parent class to the other.

##Customization vs. Added Functionality

Another way to make good decisions when deciding between inheritance and composition is the question: Customization or added functionality? When you are simply adding functionality, a category (composition) is your best bet. When you are customizing an object or group of objects that are of a type (e.g. a specific model of sports car), you likely want inheritance.

##Remember: Extensions are stateless

While there are ways to get around the fact that categories do not allow you to add state (read: properties!) you should not plan to add state to your categories. In fact, if you eventually decide to learn Swift, you'll learn that you cannot make categories include state at all!


<a href='https://learn.co/lessons/ios-reading-inheritanceVsComposition' data-visibility='hidden'>View this lesson on Learn.co</a>

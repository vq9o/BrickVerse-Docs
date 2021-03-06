# Instance

{% hint style="warning" %}
**NotCreatable**

This object cannot be created with the [`Instance.new`](broken-reference) constructor function.
{% endhint %}

Instance is the base class for all classes in the BrickVerse class hierarchy. Every other class that the BrickVerse engine defines inherits all of the members of Instance. It is not possible to directly create Instance objects.

Instance has a special function called `Instance.new` which is used to create objects via code. This function takes the name of the class as a parameter and returns the created object. Abstract classes and services cannot be created with the Instance.new function.

Inherited from [Dynamic](https://docs.brickverse.co/bricklua-lua-references-manual/dymanic) Set

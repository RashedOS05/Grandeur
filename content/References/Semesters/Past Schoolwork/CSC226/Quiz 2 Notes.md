---
publish: true
created: 2025-03-19T02:28:10.743+03:00
modified: 2026-05-27T16:59:56.708+03:00
---

**Data Structures are:** Hashmaps, arrays, trees, etc...
When removing a node, LinkedLists cost less time complexity than ArrayLists due to them pointing at each other, so you only need to make the node.prev and node.next pointers readjusted, whereas in ArrayLists, you'd have to (worst case scenario) move the whole list to readjust.
**Hashmap:** Is exactly like dictionaries from [[Python]] (key-value pairs are stored inside of it).
**Ex: Map\<String, LivingBeing> ali = new HashMap\<String, LivingBeing>();**
^ This creates a map `ali` where keys are `String` and values are `LivingBeing`

**What is the purpose of generics in Java?** To allow multiple inheritance in classes.

Generics allow you to write code that works with `ANY data type` without specifying it upfront.
_Ex_: `<t>` or `<t, u>` for two parameters that could hold two different data types if need be (t & u are conventions).

**What would happen if you tried to add a `Fish` object to the `ali` map in `MainUsingMaps` with a duplicate key?**
The new `Fish` object would overwrite the existing one.
_Explanation:_ `HashMaps` do NOT allow duplicate keys.

**What is the primary difference between a `List` and a `Set` in Java?**\
A `List` allows duplicate elements, while a `Set` does not.

### **Why Are Interfaces Useful?**

1. **Standardization**: They ensure that all classes implementing the interface follow the same rules.

2. **Flexibility**: You can write code that works with any class that implements the interface (the interface cares about the implementation regardless of how it's being implemented).

3. **Multiple Behaviors**: A class can implement multiple interfaces, allowing it to have multiple behaviors (enables multiple inheritences).

The `@Override` annotation is used to indicate that a method in a subclass is **overriding** a method from its superclass or implementing a method from an interface. It tells the compiler:
_"Hey, I’m intentionally overriding this method."_

### Remember:

#### generic setter:

public void setItem(T item){
this.item = item;
}

#### generic getter:

public void getItem(T item){
return this.item;
}

[Learn Java GENERICS in 13 minutes! 📦 - YouTube]([https://youtu.be/H9vc4gTtGGA?si=lh1NtW31Go-vqNV4]\(\))
[Learn INTERFACES in 6 minutes! 📋 - YouTube](https://youtu.be/c2sTQk9opO8?si=KA1TlwYpDlnMa2-e)

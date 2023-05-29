# Abstract ethod

- a class you cannot create objects from

## Example:

- Parent: Product
- Child classes: Shirt & Pants

Making a a new instance of `Product` doesn't really serve any purpose we don't know if it is a shirt, pants or what type of product it is.

- We only want it to serve as a blueprint

```java
Product product = new product(19.99, "Blue", "NO_NAME");
```

### Making Product an abstract clas is the solution here.

What does it do?

- It still serves as a blueprint for the child Shirt and Pants classes to follow from
- You just can't make an instance of it.

## Abstract method

Purpose: is a more generalized method that all children will have but are implemented differently

- exposes behavior that a child most override
- initalize abstract method in parent class is all you do
- Specify implmentation of it in child class

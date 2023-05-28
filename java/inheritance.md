# Inheritance

`Super()`

- Calls parent contructor method

`protected` type

- children/extended classes can access variable

## Tip

- Remmber the parent classes you won't neccessarily use the class to create new objects.

- These are blue prints for the actually class you will be using. Good to modulate your code in different classes
- Ex. Worker -> Employee -> SalariedEmployee

For the most part you will be create all of the new instances using the **salaried employee** class.

## Example

- Example: You won't really be using the `Worker` class (which is the parent) to create classes.
- You will use the SalariedEmployee class as it is an instance of the parent class and is more fleshed out.
- The reason why it's like this is to seperate code and modulate it. All methods don't have to be in one class. You'll know which class to go to.

### Remember

- Each class will have it's own responsibilities
- Each instance should add more functionality to the previous class

```java
Worker ex1 = new Worker("Chris", "05/04/2002");
Employee ex2 = new Employee("John", "05/01/1991", "05/22/2020");
SalariedEmployee employe1 = new SalariedEmployee("Kate", "02/23/1997", "05/22/2020", 22000, false);
```

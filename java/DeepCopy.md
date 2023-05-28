# Deep Copying

Don't ever are returning something that is a reference.

- Ex. mutable Object
- For example if you are returning an mutatable object using a setter method you have to deep clone it because if not, you'll have direct access to the address
- Like arrays objects are accessed in memory by going to address of beginning block of code

### Mutable Objects:

- Any object that can be updateed

## Mutability:

If your object contains mutable data structures (like arrays or collections), you might need to use a deep copy to ensure that changes to these data structures in the original object do not affect the copied object.

## Immutable Objects

Don't have to Deep Copy Immutable Objects

- Integer
- Long
- Double
- Character
- Boolean
- String

Remember all of these wrapper objects makes a new object everytime you change its value so they are immutable.

We will use `String` as an example.

This Strings is mutated when you change its value.

- A new copy is made

````java
String str1 = "hi" // this is shorthand way
str1 = "hey"

// Is the same as this

String str2 = new String("hi")
str2 = new String("hey")

// It doesn't mutate, it makes a new string object
```s
````

## Real Example

```java
public class Store {
   private ArrayList<Book> books;

   public Store() {
       this.books = new ArrayList<>();
   }

   public Book getBook(Integer index) {

       return new Book(books.get(index));

       /*
       1. sets the book it gets to equal a new book
       instance that's not in this object

       2. Has the same value but now points to a different
       object in memory

       3. If I change the getBook value it would not
       affect the Book in the array in this class

       4. This is great because getBook doesn't have
       direct access to this books array
        */
   }

   public void setBook(Integer index, Book book) {
        Book newBook = new Book(book);
        this.books.set(index, newBook);
    }

        /*
       1. Outside book won't have direct access

       2. We make a new book instance

       3. Then set book at ~index to have the same
       value but different address

       4. Outside book and set book have different addresses
        */

}
```

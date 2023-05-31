# Three Layer Design

1. Presentation

- Presents information to the user
- Handles user input and output

2. Service

- Middle man between presentation and repository
- Presentaion has to go througth the service layer then service layer talks to repository
- Contains the business logic

3. Repository

- Only layer that can access the data store
- Does **_CRUD_** operations to the data store

---

Repository layer are usually POJOS

- They contains fields, getters, and setters but they don't have any methods

## Example

1. Take in user input from the presentation layer
2. the service layer will take the information and save it to the repository
3. Repository will put information into the database

---

1. In main file which would be presentation layers you take in user input from the console.
2. Ex. in the main file you would use the service classes/layer to make a new checking account based on input then validate it and have special methods for the data based on server layer.
3. You send info into repository then repository updates the database by doing CRUD operations

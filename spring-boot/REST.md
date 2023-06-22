# REST

## POST

```java
@PostMapping("/contact")
    public ResponseEntity<HttpStatus> createContact(@RequestBody Contact contact) {
        contactService.saveContact(contact);
        return new ResponseEntity<>(HttpStatus.CREATED);
    }
```

- For POST request the parameter of the function will store the body
- For GET it will store URI variables

The body of this POST Request is:

```json
{
  "name": "Jon Snow",
  "phoneNumber": "123"
}
```

The `@RequestBody` converts/deserializes the `json` into a Java object that matches `Contact` class/object

- All you need is empty constructor and getters/setter and it will take care of populating the values of `Contact`

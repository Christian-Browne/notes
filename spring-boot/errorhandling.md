# Error Handling

## Step: 1

Using `Optional<>` when recieving objects from, database

- You want to check if it is null or not
  throw a custom exception for when it can't find a `Job` object with that `id`

```java
public Job getJob(Long id) {
       Optional<Job> job = jobRepository.findById(id);
       if (job.isPresent()) {
           return job.get();
       } else {
           throw new JobNotFoundException(id);
       }
    }
```

## Step: 2

This how to create that custom exception

- The id is being passed in when you throw the exception
- the `super()` is used because `RunTimeException` will handle returning the message and stopping the program

```java
public class JobNotFoundException extends RuntimeException {
    public JobNotFoundException(Long id) {
        super("Could not find job with id of " + id);

    }
}
```

## Step: 3

Make a global exception handler for your app so you can specify how to handle the custom exceptions that are `thrown`.

```java
@ControllerAdvice
public class AppExceptionHandler {

    @ExceptionHandler(JobNotFoundException.class)
    public ResponseEntity<Object> JobNotFoundExceptionHandler(JobNotFoundException ex) {
        ErrorResponse errorResponse = new ErrorResponse(ex.getMessage(), 404);
        return new ResponseEntity<>(errorResponse, HttpStatus.NOT_FOUND);
    }

    // this handles wrong field inputs
    @ExceptionHandler(MethodArgumentNotValidException.class)
    public ResponseEntity<Object> handleValidationExceptions(MethodArgumentNotValidException ex) {
        ArrayList<String> errors = new ArrayList<>();

        ex.getBindingResult().getAllErrors().forEach((error) -> {
            String errorMessage = error.getDefaultMessage();
            errors.add(errorMessage);
        });
        ErrorResponse errorResponse = new ErrorResponse(errors, 400);
        return new ResponseEntity<>(errorResponse, HttpStatus.BAD_REQUEST);
    }
}

```

## Step: 4

Make a pojo message class so it return a JSON object is returned when a exception is thrown:

`{"message": "test", "status": 404}`

```java
public class ErrorResponse {
    private ArrayList<String> messages = new ArrayList<>();
    private long status;

    public ErrorResponse(String message, long status) {
        this.messages.add(message);
        this.status = status;
    }
    /*
    This contructor accepts array b/c there can be
    multiple errors that come in from wrong validations
    */
    public ErrorResponse(ArrayList<String> errors, long status) {
        this.messages = errors;
        this.status = status;
    }

    public ArrayList<String> getMessages() {
        return messages;
    }

    public void setMessages(ArrayList<String> messages) {
        this.messages = messages;
    }

    public long getStatus() {
        return status;
    }

    public void setStatus(long status) {
        this.status = status;
    }
}
```

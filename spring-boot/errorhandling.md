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
    public ResponseEntity<Object> JobNotFoundExceptionHandler(JobNotFoundException exception) {
        ErrorResponse response = new ErrorResponse(exception.getMessage());
        return new ResponseEntity<>(response, HttpStatus.NOT_FOUND);
    }
}

```

## Step: 4

Make a pojo message class so it return a JSON object is returned when a exception is thrown:

`{message: test status: 404}`

```java
public class ErrorResponse {
private String message;

    public ErrorResponse(String message) {
        this.message = message;
    }

    public String getMessage() {
        return message;
    }

    public void setMessage(String message) {
        this.message = message;
    }
}
```

# Security and JWT

https://youtu.be/KxqlJblhzfI

## Step: 1

Add spring security package

## Step 2:

1. Make `User` class/entity
2. Make it implement UserDetails so it can have all of the spring securtity methods

```java
@Entity
@Table(name = "user")
public class User implements userDetails {

}
```

Override the methods in the class

## Step 3:

Create a repository interface for the `User` object

## Step 4:

Create a JWT filter class that all request have to go through

```java
@Component
@RequiredArgsConstructor
public class JwtAuthFilter extends OncePerRequestFilter {
    @Override
    protect void doFilterInternal(
        @NonNull HttpServletRequest request,
        @NonNull HttpServletResponse response,
        @NonNull FilterChain filterChain
    ) throws ServletException, IOException {
        final String authHeader = request.getHeader("Authorization");
    }
}
```

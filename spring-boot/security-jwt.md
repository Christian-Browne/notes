# Security and JWT

https://youtu.be/KxqlJblhzfI

## Overview

### Filter

- All HTTP request passs through here and checks if it has JWT token
- then the filter passes it off to the JWT service

### JWT Service

- Handles all of the JWT logic and authenticates/authorizes everything
- Decrypts all the JWT info as well

### Database & Store Token

- `Filter` will check this database if `user` exist or not
- Have a database that stores the JWT token

---

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

    // create the class (go to step 5 to see how)
    private final JwtService jwtService;
    @Override
    protect void doFilterInternal(
        @NonNull HttpServletRequest request,
        @NonNull HttpServletResponse response,
        @NonNull FilterChain filterChain
    ) throws ServletException, IOException {
        // Gets the header that contains Auth information
        final String authHeader = request.getHeader("Authorization");
        final String jwt;
        final String userEmail;

        // Checks if we have JWT token or not
        // Every token starts with Bearer
        if (authHeader == null || authHeader.startsWith("Bearer ")) {
            filterChain.doFilter(request, response);
            return;
        }

        // Get's token if we have it
        jwt = authHeader.substring(7);
        userEmail = jwtService.extractUsername(jwt);
    }
}
```

## Step 5

Create `JwtService` class

- add `jjwtapi` dependency
- add `jjwt-implementation` dependency
- add `jjwt-jackson` dependency

```java
@Service
public class JwtService {

    public String extractUsername(String token) {

    }
}
```

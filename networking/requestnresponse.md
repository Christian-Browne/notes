# Request & Response

## Two ways to request a image from server

1. Send whole image to client

   - bad: if request has to resend image
   - takes up two much memeory
   - a lot of bandwith

2. Client request image from server

   - Server sends image in chunks (prefered way)

   - can be stateful

## Cons of Request & Response

- Doesn't work well with live applications
  - Ex. client will have to keep requesting (this is called polling) to check if someone commented on their IG post

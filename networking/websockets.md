# WebSockets

> Bidirectional communications on the web

Is the only one that works on browsers unlike UDP and TCP

- Web sockets is built for the web
- Built on top of HTTP
- TCP would be too much for Browsers because it could do things such as connect to SSH, FTP

Remember HTTP 1.1 keeps connection alive and doesn't close connection after a single request. Open up opportunity for **WebSockets**

### Protocol

- `wss://`

### Use cases

- Chatting
- Live feed
- Multiplayer gamming
- Showing client progress/logging

## Websocket Handshake

### Simple way

1. The client sends a WebSocket handshake request to the server.
2. The server responds with a handshake response.
3. If the handshake is successful, the WebSocket connection is established.

### More In-depth way

1. Client Sends a WebSocket Handshake Request: The client initiates the handshake by sending an HTTP request to the server. This request includes several headers, most importantly the `Upgrade header` set to websocket and the Connection header set to Upgrade. Additionally, the request should include a Sec-WebSocket-Key header with a randomly generated value to ensure security.

2. Server Responds with a Handshake Response: Upon receiving the client's handshake request, the server examines the headers to confirm that it is a valid WebSocket handshake request. If everything is in order, the server responds with an HTTP response, known as the handshake response. This response includes the Upgrade header set to websocket, the Connection header set to Upgrade, and a Sec-WebSocket-Accept header.

3. Securing the Handshake: To ensure the security of the handshake, the server constructs the value for the Sec-WebSocket-Accept header by concatenating the value of the client's Sec-WebSocket-Key header with a predefined string, and then generating a SHA-1 hash of the concatenated value. The resulting hash is then base64-encoded and set as the value of the Sec-WebSocket-Accept header in the handshake response.

4. Establishing the WebSocket Connection: Once the client receives the handshake response, it verifies the Sec-WebSocket-Accept header to ensure the handshake is valid. If the verification is successful, the client and server are considered to have successfully completed the WebSocket handshake, and the connection is established.

5. WebSocket Communication: After the handshake, both the client and the server can start sending WebSocket frames over the established connection. These frames can contain various types of data, such as text, binary, or control frames, and are used for bidirectional communication between the client and the server.

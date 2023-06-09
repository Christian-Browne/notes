# HTTP/1.1

- built on top of TCP
- Still does three way handshake
- https does TLS handshake
  - http doesn't

## HTTP Request Has Three Things

### Method:

The method specifies the type of action to be performed on the resource identified by the URL. Common HTTP methods include GET, POST, PUT, DELETE, PATCH, and OPTIONS.

### PATH:

The path indicates the specific location or endpoint on the server where the requested resource is located. It is a part of the URL that comes after the domain name.

### Protocol:

The protocol defines the rules and conventions for communication between the client (e.g., web browser) and the server. In the case of HTTP, the most commonly used protocol is HTTP or HTTPS (secure version of HTTP).

### Headers:

Headers provide additional information about the request, such as the type of data being sent, the acceptable response formats, authorization credentials, and more. They are key-value pairs that are included in the request's header section.

### Body:

The body contains the data or payload sent along with the request, typically used with methods like POST, PUT, or PATCH. It carries the information to be processed by the server. The body can be in various formats such as JSON, XML, or plain text, depending on the content type specified in the request's headers.

## HTTP Response

### Protocol:

HTTP (Hypertext Transfer Protocol) is the underlying protocol used for communication between a client (such as a web browser) and a server. It defines the rules and formats for requests and responses.

### Code:

The HTTP response includes a status code, which is a three-digit number that indicates the outcome of the request. The status code provides information about whether the request was successful, encountered an error, or requires further action.

### Code Text:

The code text is a brief description or message associated with the status code, providing more details about the outcome of the request. For example, a status code of 200 may have a code text of "OK" indicating a successful response, while a status code of 404 may have a code text of "Not Found" indicating that the requested resource was not found on the server.

### Headers:

The HTTP response also includes headers, which are additional metadata or information about the response. Headers can provide details about the server, caching, content type, encoding, cookies, and other important information.

### Body:

The body of the HTTP response contains the actual content being sent back from the server. This can include HTML markup, JSON data, images, files, or any other type of data. The body carries the information requested by the client or the response to a specific action. The format and structure of the body depend on the specific content being transmitted.

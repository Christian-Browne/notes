# UDP (User Datagram Protocol)

UDP is a transport protocol in computer networking that operates on the Transport Layer of the Internet Protocol Suite. Unlike TCP (Transmission Control Protocol), UDP is a connectionless and unreliable protocol. It means that UDP does not establish a persistent connection between the sender and receiver and does not guarantee the delivery or ordering of packets.

UDP is often used in scenarios where low-latency communication is required, and a small amount of data loss can be tolerated, such as real-time video streaming, voice over IP (VoIP), online gaming, DNS queries, and more.

## Video Streaming Example

In the context of video streaming, UDP can be utilized to transmit video data from a server to a client. Here's a simplified example of how UDP can be used for video streaming:

1. The video server divides the video file into small packets.
2. Each packet is assigned a sequence number and contains a portion of the video data.
3. The video packets are sent as UDP datagrams from the server to the client.
4. The client receives the UDP packets and processes them individually.
5. The client reconstructs the video frames using the received packets, using techniques like buffering, decoding, and rendering.
6. The reconstructed video frames are displayed to the user in real-time.

UDP is suitable for video streaming because it offers low overhead and minimal latency. It allows for faster transmission of video data compared to protocols like TCP, where the overhead of establishing a connection and ensuring reliable delivery can introduce additional delay.

## How UDP is different than Websockets

Websockets, on the other hand, are a communication protocol that enables full-duplex communication between a client and a server over a single, long-lived connection. Unlike UDP, websockets are built on top of TCP and provide a reliable, bidirectional, and message-oriented communication channel.

Websockets are commonly used in scenarios where real-time, interactive communication is required, such as chat applications, collaborative editing, live updates, and more. They are particularly suitable for applications that need real-time bidirectional communication, unlike the unidirectional nature of UDP.

Compared to UDP, websockets provide additional features like reliable delivery, automatic reconnection, and support for structured messages. These features make websockets more suitable for applications that require guaranteed delivery and bidirectional communication, even if they introduce more overhead and latency compared to UDP.

## Summary

In summary, while UDP is often used for low-latency, loss-tolerant scenarios like video streaming, websockets provide a reliable, bidirectional communication channel suitable for real-time interactive applications. The choice between UDP and websockets depends on the specific requirements of the application and the trade-offs between latency, reliability, and communication features.

## Java Example

```java
import java.net.DatagramPacket;
import java.net.DatagramSocket;

public class UDPServer {
    public static void main(String[] args) {
        try {
            DatagramSocket socket = new DatagramSocket(5000);
            byte[] buffer = new byte[1024];
            DatagramPacket packet = new DatagramPacket(buffer, buffer.length);

            System.out.println("Server started. Listening for incoming messages");

            while(true) {
                socket.receive(packet);

                String message = new String(packet.getData(), 0, packet.getLength());
                System.out.println("Received: " + message);
            }

        } catch (Exception e) {
            e.printStackTrace();
        }

    }
}
```

### Test

```bash
nc -u 127.0.0.1 5000
```

Connect to server by a client by doing this in terminal

- `-u` means you are in udp mode

## Explanation of the Code

1. First, the necessary packages are imported: `java.net.DatagramPacket` and `java.net.DatagramSocket`. These packages provide classes for working with UDP sockets and packets.

2. The `main` function is declared with the `public static` modifiers, indicating that it is a class-level method and can be called without creating an instance of the class.

3. Inside the `try` block, a `DatagramSocket` is created by initializing it with the port number 5000. This socket will be used for sending and receiving UDP packets.

4. A byte array called `buffer` is created with a length of 1024. This buffer will hold the data received from the client.

5. A `DatagramPacket` object called `packet` is created, passing the `buffer` and its length as arguments. This packet will be used to store the incoming data from the client.

6. The server prints a message to indicate that it has started and is listening for incoming messages.

7. A `while` loop is started with the condition `true`, which means it will continue indefinitely until an exception occurs or the program is terminated.

8. Inside the loop, the `socket.receive(packet)` method is called. This method blocks until a packet is received from a client. The received data is stored in the `packet` object.

9. The received data is then extracted from the `packet` and converted to a `String` using the `String` constructor. The `packet.getData()` method returns the byte array, `packet.getLength()` returns the length of the received data, and `new String(...)` converts the byte array to a string.

10. The received message is printed to the console using `System.out.println()`.

11. The loop continues, and the server waits for the next incoming packet.

12. If an exception occurs during the execution of the `try` block, it is caught by the `catch` block. The exception is printed to the console using `e.printStackTrace()`.

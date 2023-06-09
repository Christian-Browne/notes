# TCP: Transmission Control Protocol

> Vehicle of choice between any client and backend application

- The most popular protocol
- Has more overhead than UDP
- Stateful

- You will know that the data has arrived
- Each packet is sequenced so you can keep track even when they arrive out of order

## Three way handshake

Client sends > server sends back > clients sends back with data

## Summary

TCP stands for Transmission Control Protocol, and it's one of the main protocols in the Internet protocol suite. TCP is a connection-oriented protocol, which means it establishes and maintains a network connection until the applications at each end have finished exchanging messages. It determines how to break application data into packets that networks can deliver, sends packets to and accepts packets from the network layer, manages flow control, and—because it is meant to provide error-free data transmission—handles retransmission of dropped or garbled packets as well as acknowledgement of all packets that arrive.

## Here are some of the key features of TCP:

- **Connection-oriented**: Before any data transfer can happen, a reliable connection is established between the sender and the receiver. This is known as the TCP three-way handshake.

- **Reliable**: TCP ensures a reliable transfer of data. If any data is lost during transmission, TCP has a system of acknowledgments and timeouts to detect these issues and retransmit the lost data.

- **Ordered packets**: TCP rearranges data packets in the order they were sent. This is crucial for applications that need data to be delivered in order.

- **Error-checked**: TCP includes error checking and error recovery functionalities. Any corrupted sections of data are re-sent and replaced.

- **Flow control**: TCP uses a sliding window for flow control, which helps manage the amount of data that can be sent before needing an acknowledgement.

## Examples of TCP usage:

- **Web Browsers**: When you're browsing the internet, your browser is likely using HTTP or HTTPS over TCP to request and receive web pages from servers.

- **Email**: Email protocols like SMTP, POP3, and IMAP use TCP for sending and receiving emails.

- **File Transfers**: Protocols like FTP and SFTP for sending and receiving files use TCP to ensure the data arrives accurately and in order.

- **Secure Shell (SSH)**: The SSH protocol, which is used for securely accessing remote machines, uses TCP to ensure reliable, ordered delivery of commands and responses.

In all these cases, the use of TCP allows these applications to focus on their specific tasks without worrying about the details of ordered, error-checked, and reliable data transfer, because the TCP layer handles these issues.

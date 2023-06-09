# Java Example

```java
public class TCPServer2 {
    public static void main(String[] args) {
        try {
            ServerSocket server = new ServerSocket(4444);
            System.out.println("Server Listening...");
            Socket client = server.accept();
            System.out.println("Client Connected...");

            BufferedReader reader = new BufferedReader(new InputStreamReader(client.getInputStream()));
            PrintWriter writer = new PrintWriter(client.getOutputStream(), true);

            String inputLine;
            // If you exit client it will send null then close server
            while ((inputLine = reader.readLine()) != null) {
                System.out.println(inputLine);
            }

            System.out.print("Connection ended");
            client.close();
            server.close();
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

## Steps

### Step 1 - Creating the Server Socket

```java
ServerSocket server = new ServerSocket(4444);
System.out.println("Server Listening...");
```

This section of code creates a new ServerSocket object. The ServerSocket is instantiated with the port number 4444. This is the port on which the server will be listening for incoming client connections. The "Server Listening..." message is printed to the console to indicate that the server has started and is waiting for connections.

### Step 2 - Accepting Client Connection

```java
Socket client = server.accept();
System.out.println("Client Connected...");
```

The accept method of the ServerSocket object is called, which causes the server to block, or wait, until a client connects to it. Once a client has connected, a Socket object representing the client's connection to the server is returned. The "Client Connected..." message is printed to the console to indicate that a client has connected to the server.

### Step 3 - Setting up I/O Streams

```java
BufferedReader reader = new BufferedReader(new InputStreamReader(client.getInputStream()));
PrintWriter writer = new PrintWriter(client.getOutputStream(), true);
```

This section of code sets up the input and output streams for the client connection. A BufferedReader is created to read data from the client, and a PrintWriter is created to send data to the client. The streams are tied to the InputStream and OutputStream of the Socket object, which represent the input and output channels of the connection.

### Step 4 - Receiving Data

```java
String inputLine;
// If you exit client it will send null then close server
while ((inputLine = reader.readLine()) != null) {
    System.out.println(inputLine);
}
```

The server enters a loop where it reads data from the client one line at a time using the readLine method of the BufferedReader. Each line of data is stored in the inputLine string. If the client sends a null message (indicating the connection has been closed), the loop will exit. Each line of data received from the client is printed to the console.

Note: If the client simply doesn't send any message but the connection is still alive, the server will block on reader.readLine(), meaning it will wait at this line until a message is received or the client disconnects.

### Step 5 - Closing Connections

```java
System.out.print("Connection ended");
client.close();
server.close();
```

Once the client has disconnected, the server prints a "Connection ended" message to the console, and then closes the client Socket and the ServerSocket. This is an important step to free up system resources.

### Error Handling

```java
} catch (Exception e) {
    e.printStackTrace();
}
```

## Multiple Connections on a Server

```java
public class TCPServer2 {
    public static void main(String[] args) {
        try {
            ServerSocket server = new ServerSocket(4444);
            System.out.print("Server Listening...\n");

            // This is the client handler not the client
            // makes a new thread everytime new client connects to server
            // `nc` command in the terminal is the client
            while (true) {
                // This is not making a new client
                new ClientHandler(server.accept()).start();
            }

        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}

/**************************************************************/

// Thsi class handles the client, it doesn't make a new one
public class ClientHandler extends Thread {
    private Socket client;
    private BufferedReader reader;
    private PrintWriter writer;

    public ClientHandler(Socket socket) {
        this.client = socket;
    }

    @Override
    public void run() {
        try {
            // Makes a new BufferedReader and printWriter for every unique client that connects
            // makes new I/O on the server on different threads
            reader = new BufferedReader(new InputStreamReader(client.getInputStream()));
            writer = new PrintWriter(client.getOutputStream());

            String inputLine;
            // If you exit client it will send null then close server
            while ((inputLine = reader.readLine()) != null) {
                System.out.println(inputLine);
            }

            reader.close();
            writer.close();
            client.close();
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}

```

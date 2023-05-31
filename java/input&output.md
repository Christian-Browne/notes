# Input & Output (I / O)

- goto bottom for best way

> In I/O, a stream is a channel for data to flow between a program and an input or output source, simplifying reading from or writing to different devices.

## Input Stream Bytes

- interprets each charcter in file as a byte
- Input Stream is a abstract class
- `FileInputStream` says to take input in as **bytes** (subclass of Input Stream)

```java
byte[] array = new byte[50];
InputStream input = new FileInputStream("src//text.txt");

input.read(array); // Reads each byte and stores it into byte array
String data = new String(array); // Converts each byte from array into string
System.out.println(data); // prints to console
```

### Can also do this using a loop

```java
FileInputStream input = new FileInputStream("input.txt");

System.out.println("Data in the file: ");

// Reads the first byte in the file and stores in i
int i = input.read();

// .read() returns -1 when there is nothing left to be read
while(i != -1) {
    System.out.print((char)i);

    // Reads next byte from the file
    // everytime read is called it will read next byte
    i = input.read();
}
input.close();
```

## Output Stream Bytes

```java
String data = "Write this to file";
OutputStream output = new FileOutputStream("src//text.txt");
/*
OutputStream output = new FileOutputStream("src//text.txt", true);
optinal bool value if set; will append to file instead of overwritten it
*/

byte[] streamOfBytes = data.getBytes(); // Converts string into array/stream of bytes
output.write(streamOfBytes); // writes stream to the file

System.out.println("Data Completed writing to file ");
output.close();
```

### methods

- read() - reads one byte of data from the input stream
- read(byte[] array) - reads bytes from the stream and stores in the specified array
- available() - returns the number of bytes available in the input stream
- mark() - marks the position in the input stream up to which data has been read
- reset() - returns the control to the point in the stream where the mark was set
- markSupported() - checks if the mark() and reset() method is supported in the stream
- skips() - skips and discards the specified number of bytes from the input stream
- close() - closes the input stream
- flush() - ensures text is immediately written into file instead of being held in buffer

## Object Streams

Converts Java objects into a input/output streams by `Serializing` them.

- makes it so we don't have to _explicitly_ convert object to bits before we write to file.

> Remember a String is a object in Java

- In the given context, serialization refers to the process of converting Java objects into a format that can be easily stored, transmitted, or reconstructed.
- When objects are serialized, their state (data) is converted into a stream of bytes, which can then be saved into files, sent over a network, or stored in a database.
- Serialization enables you to save or transmit the object's data along with its structure, allowing it to be reconstructed later when needed.

> Can sen Objects to a file and read Objects from a file

```java
int data1 = 5;
String data = "Cool text";

OutputStream file = new FileOutputStream("src//text.txt");
// can  write bytes to the file

ObjectOutputStream output = new ObjectOutputStream(file);
// allows us to use object stream to write objects to file then
// specify what file to write to

output.writeInt(data1);
output.writeObject(data); // Serializes Object then writes to file

System.out.println("Data Completed writing to file ");

// Remember to close both
file.close();
output.close();
```

### Cool thing

If there are objects in the file and you want to read the objects

```java
FileInputStream fileStream = new FileInputStream("file.txt");

// Creates an ObjectInputStream, then speicfy file
ObjectInputStream input = new ObjectInputStream(fileStream);

// Reads the objects and typecast to Dog Object
Dog newDog = (Dog) input.readObject();

// can now call methods on it
newDog.breed
```

### methods

read & write

- read() - reads a byte of data from the input stream
- readBoolean() - reads data in boolean form
- readChar() - reads data in character form
- readInt() - reads data in integer form
- readObject() - reads the object from the input stream

# Print Stream

A more easier method to use

- handles the conversion to bytes for us

```java
PrintStream file = new PrintStream("output.txt");

String data = "This is a text inside the file.";

file.print(data);
file.close();
```

## Buffers

reads data (in bytes) more efficiently

Buffering is more efficient because it reduces the number of direct read or write operations by storing data in a buffer and performing batch operations, reducing the overhead of individual I/O calls.

By minimizing the frequency of accessing the underlying I/O device, buffering can significantly improve performance, especially when dealing with small or frequent I/O operations.

Buffering allows for non-blocking and deferred processing of data by storing it temporarily in a buffer, decoupling the input/output operations from the actual processing, thereby enabling the program to continue execution without waiting for each individual data transfer or processing to complete immediately.

> Buffers are implemented exaclty the same jusy use

```java
// Creates a FileInputStream
FileInputStream file = new FileInputStream("input.txt");

// Creates a BufferedInputStream
BufferedInputStream input = new BufferedInputStream(file);

// Reads data from the buffer not OG file
int i = input .read();
```

# File Writer and Reader

- If you want to write and read strings from files this is the best one
  - Specifially designed to write strings and characters
- Even though `outputStream` can do th esame thing. it is typically used for byte data

### Writing to file

```java
public static void main(String[] args) {
    ArrayList<String> names = new ArrayList<>(Array.asList("John", "Carl"))

    try {
        FileWriter file = new FileWriter("src/text");
        // file you want to write to
        BufferedWriter writer = new BufferedWriter(file);
        // makes a buffer in the file so it can be more efficient
        // refer to buffer from here on out

        writer.write("This is first line");
        writer.write("\n new line");

        // can loop over array list
        names.forEach(name -> writer.write(name));

        writer.close();

    } catch (IOException e) {
        e.printStackTrace();
    }
}
```

### Reading from file

```java
FileReader file = new FileReader("src/text");
BufferedReader reader = new BufferedReader(file);

// reads first line
System.out.println(reader.readLine())

String line;
// to read everyline
while((reader.readLine()) != null) {
    System.out.println(line)

}

// save readline in variable because everytime we call readline it goes to the next line.
// we wan't to store every line
```

## Creating files

To create a new file, we can use the createNewFile() method. It returns

`true` if a new file is created.

`false` if the file already exists in the specified location.

```java
// create a file object for the current location
// doesn't actually make file yet
File file = new File("newFile.txt");

try {
    // creates file then returns true if it did, false if didn't
    // trying to create a file based on the object
    boolean value = file.createNewFile();
    if (value) {
    System.out.println("The new file is created.");
    }
    else {
    System.out.println("The file already exists.");
    }
}
catch(Exception e) {
    e.getStackTrace();
}
```

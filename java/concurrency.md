# Concurrency

- Making progress on more than one task at a time.

- Multi-threading helps achive concurrency

In Java eveyrthing is run on one thread by default. The main thread.

## Serial Execution

- Running tasks one at a time.

## Concurrent Execution

- making progress on more than one task at a time.

## First way

```java
public class Main {
    public class LongTask implements Runnable {
            @Override
            public void run() {
                // Call long function here
            }
    }

    void main() {
        LongTask runnable = new LongTask();
        Thread thread2 = new Thread(runnable);
        thread2.start();
    }
}
```

## Second way

- When interface only holds one method
- Call function you want to run on another thread as a lamda

```java
Thread thread2 = new Thread(() -> longTask());
Thread thread2 = new Thread(runnable);
```

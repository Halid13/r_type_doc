# UdpClient Documentation

***Description***

The UdpClient class is a part of the R-Type project. It represents a UDP client that communicates with a server using sockets. The class provides methods for initializing the client, sending and receiving data, and managing the game loop.

* Header File

```cpp
#include "../../include/Client/UdpClient.hpp"
```

## Constructors

### UdpClient(Address serverAddress, Address::Port clientPort)

Constructor for the UdpClient class. It initializes the UDP client with the specified server address and client port.

**Parameters:**

- `serverAddress`: The address of the server to connect to.
- `clientPort`: The port that the client will use to communicate with the server.

### UdpClient(Address::Port clientPort)

Constructor for the UdpClient class. It initializes the UDP client with the specified client port. The server address will be set to 0.

**Parameters:**

- `clientPort`: The port that the client will use to communicate with the server.

## Public Methods

### void stop() noexcept

Stops the execution of the UDP client by setting the looping variable to false.

### void reset() noexcept

Resets the UDP client by setting the looping variable to true.

### void run()

Runs the UDP client by joining the game and network threads.

### void communicate() noexcept

Waits for data to be received or sent and calls the appropriate functions accordingly.

### void gameLoop() noexcept

Runs the game loop. When the user presses the escape key, it sends a CLOSE_VALUE to the server.

### void receive()

Receives data from the socket and handles it.

### void send()

Sends data if there is any in the dataToSend queue.

### RawData getDataFromQueue() noexcept

Returns the first element of the dataToSend queue and removes it from the queue.

### void handleData(ReceivedInfos infos) noexcept

Handles the received data by parsing it and pushing GamePacket objects into the dataReceived queue.

### void checkServerConnection() noexcept

Checks if the server is still connected to the client.

## Example Usage

```cpp
#include "../../include/Client/UdpClient.hpp"

int main()
{
    // Create a UDP client with server address and client port
    Address serverAddress("127.0.0.1", 12345);
    Address::Port clientPort = 54321;
    UdpClient client(serverAddress, clientPort);

    // Run the UDP client
    client.run();

    return 0;
}
```

Note: The above example assumes that the necessary header files and libraries are included and linked properly.
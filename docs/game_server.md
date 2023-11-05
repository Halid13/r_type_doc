## Server Documentation

***Introduction***

The `Server` class represents a server that listens for client connections, receives and sends data to clients, and runs a game loop. It provides functions to start and stop the server, handle client communication, and manage client connections.

### Public Member Functions

#### Server(Address::Port port)
The constructor of the `Server` class. It creates a socket and a selector, adds the socket to the selector, and starts the game and network threads.

**Parameters:**
- `port`: The port to listen on.

#### void stop() noexcept
Stops the server. It sets the `looping_` flag to false, which will cause the server to exit the game and network loops.

#### void reset() noexcept
Resets the server to its initial state. It sets the `looping_` flag to true.

#### void run()
The run function joins the game and network threads. It waits for both threads to finish before returning.

### Private Member Functions

#### void communicate() noexcept
The `communicate` function is responsible forhandling client communication. It waits for a client to connect, then waits for a client to send a message, then sends a message to the client, and finally checks if the client is still connected.

#### void gameLoop() noexcept
The `gameLoop` function runs the game loop and sends the data to the clients. It is responsible for updating the game state and sending the updated state to all connected clients.

#### void receive()
The `receive` function receives data from the client and handles it. It checks if the client is known to the server, and if not, it adds the client to the list of connected clients. It then handles the data received from the client.

#### void send() noexcept
The `send` function sends data to the clients. If there is data to send in the send queue, it sends the data to the respective clients.

#### void sendToClient(Client& client, RawData blob)
The `sendToClient` function sends a blob of data to a client. It takes the client object and the data to send as parameters.

#### RawData getDataFromQueue(Client& client) noexcept
The `getDataFromQueue` function retrieves the first element from the send queue of a client and returns it. It takes the client object as a parameter.

#### void handleData(ReceivedInfos infos) noexcept
The `handleData` function handles the data received from the client. It takes a struct containing the address of the client and the received data as a parameter.

#### bool isKnownClient(Address address) const
The `isKnownClient` function checks if a client with the given address is known to the server. It returns true if the client is known, and false otherwise.

#### void addClient(Address address, std::chrono::high_resolution_clock::time_point ping) noexcept
The `addClient` function adds a new client to the server. It takes the address of the client and the time the client sent the ping as parameters.

#### void removeClient(Address& clientAddress) noexcept
The `removeClient` function removes a client from the server. It takes the address of the client to remove as a parameter.

#### void areClientsConnected() noexcept
The `areClientsConnected` function checks if clients are still connected to the server. If a client hasn't sent a ping in a while, it sends a ping to the client. If the client doesn't respond to the ping, it disconnects the client.

#### void updateClientState(Address& clientAddress, bool isPing) noexcept
The `updateClientState` function updates the state of a client based on the received message. If the client is found in the list of clients, it sets the `isPingSent` flag to false. If the client sent a ping, it sends a pong back.

### Member Variables

The `Server` class has several private member variables that are used to manage client connections and handle communication:

- `socket_`: An instance of the socket class used for server communication.
- `selector_`: An instance of the selector class used to monitor multiple sockets for activity.
- `clients_`: A vector of client objects representing the connected clients.
- `sendQueue_`: A queue of data to be sent to the clients.
- `looping_`: A boolean flag indicating whether the server is running or stopped. If `looping_` is true, the server is running, and if `looping_` is false, the server is stopped.

These member variables are used internally by the server to manage client connections, handle communication, and run the game loop.
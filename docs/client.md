# Class ClientENet

The ClientENet class is responsible for creating and managing an ENet client using the ENet library for network communication.

## Methods
* ClientENet()

The constructor of the ClientENet class initializes the ENet library by calling the enet_initialize() function. If initialization fails, an error message is printed.

* ~ClientENet()

The destructor of the ClientENet class disconnects from the server by calling the Disconnect() method and releases the resources used by the ENet library by calling the enet_deinitialize() function.

* Connect(const char* serverAddress, int port)

The Connect method connects the client to the server. It takes a serverAddress parameter as a string representing the server's IP address and a port parameter as an integer representing the server's port number.

The method performs the following operations:

    If the client is already connected, it disconnects first by calling the Disconnect() method.
    Sets the server's address using the enet_address_set_host() function.
    Creates an ENet host using the enet_host_create() function with parameters (null for the address, 1 channel for outgoing traffic, 2 channels for incoming traffic, no outgoing bandwidth limit, no incoming bandwidth limit).
    If the host creation fails, an error message is printed, and the method returns false.
    Connects to the server using the enet_host_connect() function.
    If the connection to the server is successful, the method waits for an event using the enet_host_service() function. If a connection event is received within 5 seconds, a success message is printed, and the method returns true. Otherwise, a failure message is printed, and the method returns false.

* Disconnect()

The Disconnect method disconnects the client from the server. It resets the peer using the enet_peer_reset() function, flushes the host using the enet_host_flush() function, destroys the host using the enet_host_destroy() function, and sets the client and peer pointers to null. A disconnection message is printed.

* IsConnected()

The IsConnected method checks if the client is connected to the server. It returns true if both the client and peer pointers are not null; otherwise, it returns false.

* SendData(const void* data, size_t dataSize)

The SendData method sends data to the server. It takes a data parameter as a pointer to the data to be sent and a dataSize parameter as the size of the data.

The method performs the following operations:

    Checks if the client is connected.
    Creates an ENet packet using the enet_packet_create() function with the data, data size, and reliable flag.
    Sends the packet to the peer using the enet_peer_send() function.
    Flushes the host using the enet_host_flush() function.

* Update()

The Update method updates the client by handling incoming network events. It checks if the client is connected and then enters a while loop to process events using the enet_host_service() function.

The method performs the following operations:

    Checks if the client is connected.
    Waits for an event using the enet_host_service() function.
    Processes the event based on its type:
        ENET_EVENT_TYPE_RECEIVE: Handles received data by destroying the packet.
        ENET_EVENT_TYPE_DISCONNECT: Handles disconnection by calling the Disconnect() method.

* main() function

The main function is the entry point of the program. It creates an instance of the ClientENet class and a Window object. It retrieves the server address and port from the command-line arguments. If the client successfully connects to the server, it sends data to the server, runs the window, and enters a loop to update the client while it is connected. If the connection fails, the client is disconnected.

Please note that to use this code, you need to include the "Client.hpp" header file and the ENet library using #include <enet/enet.h>. Also, make sure you have the ENet library installed and properly configured.
# Class

The ENetServer class is responsible for creating and managing an ENet server using the ENet library for network communication.

## Methods
* ENetServer()

The constructor of the ENetServer class initializes the ENet library by calling the enet_initialize() function. If initialization fails, an error is printed, and the program exits with a EXIT_FAILURE exit code.
* ~ENetServer()

The destructor of the ENetServer class releases the resources used by the ENet library by calling the enet_deinitialize() function.
startServer(int port)

The startServer method starts the ENet server. It takes an integer port parameter that specifies the port number on which the server should listen for incoming connections.

The method performs the following operations:

    Initializes an ENetAddress structure with the server's IP address (in this example, "10.50.6.84") and the port number passed as a parameter.
    Creates an ENet host using the enet_host_create() function with the address and additional parameters (32 channels, 2 incoming connections, no outgoing bandwidth limit, no incoming bandwidth limit).
    If the host creation fails, an error is printed, and the program exits with a EXIT_FAILURE exit code.

* run()

The run method is responsible for the main execution of the server. It uses an infinite while loop to wait for and handle network events.

The method performs the following operations:

    Waits for a network event using the enet_host_service() function.
    If an event is received, it is processed based on its type:
        ENET_EVENT_TYPE_CONNECT: Prints a message indicating that a client has connected.
        ENET_EVENT_TYPE_RECEIVE: Prints a message indicating that a packet has been received from the client, then destroys the packet using the enet_packet_destroy() function.
        ENET_EVENT_TYPE_DISCONNECT: Prints a message indicating that a client has disconnected.
    The loop continues to wait for new events.

* stopServer()

The stopServer method stops the ENet server by destroying the ENet host using the enet_host_destroy() function.

* main() function

The main function is the entry point of the program. It creates an instance of the ENetServer class, starts the server by calling the startServer() method with the port number passed as a command-line argument (av[1]), and runs the server by calling the run() method. Finally, the main function returns 0 to indicate successful execution.

Please note that to use this code, you need to include the "Serveur.hpp" header file and the ENet library using #include <enet/enet.h>. Also, make sure you have the ENet library installed and properly configured.
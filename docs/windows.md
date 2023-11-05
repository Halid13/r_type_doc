# WindowsSocket Documentation

The `WindowsSocket` class provides an implementation of a UDP socket that is compatible with Windows operating systems. It allows for sending and receiving data over UDP.

***Constructor***

### `WindowsSocket(Address::Port port)`

This constructor initializes a UDP socket and binds it to the specified port. It also reserves memory for the received buffer.

#### Parameters

- `port` (Address::Port): The port to bind the socket to.

#### Exceptions

- `InitError`: Thrown if the initialization of the socket fails.

***Destructor***

### `~WindowsSocket() noexcept`

The destructor for the `WindowsSocket` class. It cleans up the socket resources and closes the socket.

## Public Member Functions

### `ISocket::Fd getSocketFd() const noexcept`

This function returns the socket file descriptor.

#### Return Value

- `ISocket::Fd`: The socket file descriptor.

### `Address getAddress() const noexcept`

This function retrieves the local address to which the socket is bound.

#### Return Value

- `Address`: The local address.

### `void send(const void* data, int data_size, Address destAddr) const`

This function sends data to a specified destination address.

#### Parameters

- `data` (const void*): A pointer to the data to be sent.
- `data_size` (int): The size of the data to be sent.
- `destAddr` (Address): The address of the destination.

#### Exceptions

- `NetworkError`: Thrown if an error occurs while sending data.

### `ReceivedInfos receive()`

This function receives data from a client and returns information about the received data.

#### Return Value

- `ReceivedInfos`: A struct containing the sender's address and the received data.

#### Exceptions

- `NetworkError`: Thrown if an error occurs while receiving data.

## Static Member Functions

### `Address winAddressToAddress(SOCKADDR_IN address) noexcept`

This static function converts a Windows socket address to a cross-platform address.

#### Parameters

- `address` (SOCKADDR_IN): The Windows socket address to convert.

#### Return Value

- `Address`: The converted cross-platform address.

### `SOCKADDR_IN addressToWinAddress(Address address) noexcept`

This static function converts an `Address` object to a Windows `SOCKADDR_IN` object.

#### Parameters

- `address` (Address): The address to convert.

#### Return Value

- `SOCKADDR_IN`: The converted Windows socket address.

---

*Note: The code provided is specific to Windows platforms and utilizes the Windows Sockets API (WSA). It may not be compatible with other operating systems.*
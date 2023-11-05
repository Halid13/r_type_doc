# Welcome to R-TYPE

The goal is to implement a multithreaded server and a graphical client for a well-known legacy video game called R-Type, using a game engine of your own design.

Language: Advanced C++

## Build tool
The project must be built using a CMake and dependencies must be handled using conan.

## Graphique
We used SFML for client-side displays and all rendering was done using SFML.

## Network
The network library is the package that enables the various clients to communicate with the server and play with their friends.
The principle is simple: you connect via TCP, which manages several game servers using the UDP protocol.
The client is then directly redirected to an available game server and switches to UDP communication to play.

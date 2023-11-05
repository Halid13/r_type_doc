<h1 align="center">
  <img src="https://upload.wikimedia.org/wikipedia/fr/6/64/R-Type_Logo.png" alt="Depviz" title="Depviz" height="200px">
</h1>

## About the project

This project aims to recreate the cross-platform video game R-Type with an online mutiplayer mode.
It required the implementation of a multithreaded server and a graphical client, using an engine of our own design.

- `Tools:`
  - Project made in `C++` version 20
  - use of the `SFML` graphical library to display game elements
  - Compiled with `CMake`, minimum version required : `3.17`
  - `GITHUB Actions` for automatique tests
  - `MK Docs` for documentation
  - A `Script` is provided to compile, run and test the project

- Some of the features we implemented:
  - A `multithreaded` server, to handle communication and game logic at the same time
  - A generic `Entity Component System` architecture and game engine
  - A graphical client, to display the game and handle user input
  - A client-server communication protocol
  - A network building with `ENet` for the connection

## Build tool
The project must be built using a CMake and dependencies must be handled using conan.

## Installation

**Tools:**

Ensure that you have cmake and enet installed in your pc

**Linux:**

```sh
./run.sh
```

## Graphique
We used SFML for client-side displays and all rendering was done using SFML.

## Network
The network library is the package that enables the various clients to communicate with the server and play with their friends.

## How to play
Once the game is launched, we enter the server's IP address and the port it is connected to. Then, the game can begin.

* To move the player `upwards`, we use the directional key: `up`.
* To move the player `downwards`, we use the directional key: `down`.
* To move the player to the `right`, we use the directional key: `right`.
* To move the player to the `left`, we use the directional key: `left`.
* To `shoot`, we use the key: `space`.
* To `spawn` enemies, we use the key: `enter`.

## UML

* **Serveur:**
[Architecture](https://draft.io/g85bjfcfgg4ja6kzunezzf76utkzbqgkx2a6fa9j95zp)
* **Client:**
[Architecture](https://draft.io/g85bjfcfgg4ja6kzunezzf76utkzbqgkx2a6fa9j95zp)
* **Entity:**
[Architecture](https://draft.io/g85bjfcfgg4ja6kzunezzf76utkzbqgkx2a6fa9j95zp)
* **Components:**
[Architecture](https://draft.io/g85bjfcfgg4ja6kzunezzf76utkzbqgkx2a6fa9j95zp)
* **System:**
[Architecture](https://draft.io/g85bjfcfgg4ja6kzunezzf76utkzbqgkx2a6fa9j95zp)


## Game improvements
- Want to create your own custom levels ? Check out our [Level's guide](docs/CustomLevel.md) !

## Licence

**MTI Licence**
Copyright (c) 2012-2023 Scott Chacon and others
[Licence](https://github.com/EpitechPromo2026/B-CPP-500-COT-5-1-rtype-leobasthene.lima/blob/main/docs/LICENCE.md)

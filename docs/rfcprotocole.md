# Protocole RFC

   This note is the official specification for the two R-Type protocols (the R-Type TCP protocol and the R-Type UDP protocol).

***Introduction***

   The aim of the R-Type project is to create an online multiplayer copy of the classic multiplayer online game R-Type (1987).

## R-Type architecture

R-Type's architecture is a classic client-server game architecture 
architecture. The entire game engine is located in the server. A client
connects connects to the server using the R-Type TCP protocol. Once
connected, the client can choose between creating a new lobby or joining
an existing one. Several clients can connect to the server at the same
time. Next, the customer who created the lobby can start a new game. The
server can run several games at the same time.

## R-Type TCP Protocol

All client-server communication prior to game launch is carried
   out using this using this R-type TCP protocol.

   These codes define the different actions that we will observe at the 
  with the action assigned to each function.

      The ACTION enumeration:

         enum ACTION {
            500 = KO,
            230 = CONNECT,
            332 = JOIN,
            201 = READY,
            200 = START,
            221 = DECONNECTION,
	        250 = MOVE,
            257 = SHOOT,
            530 = QUIT,
	        211 = LEFT,
            212 = RIGHT,
            213 = UP,
            214 = DOWN
         };

      To send a payload, each piece of data must be written to the
      socket so that the actions behind it can be executed.

## Code explanations

To explain what's going on, we need to understand that these
      different codes have a very precise meaning for the customer.

    In this way, the customer relies on these various codes to
    respond to the instructions.

	500 = KO : This allows the customer to understand that the
   message has not not reached its destination. So there's an error
   in the message reception

	230 = connect : This tells the client that it has successfully
    connected to the server, enabling further communication.

	332 = join : This allows you to manage the integration of a new 
   a new player into an existing or exixtante game.

	201 = ready : This code is used to recognize at customer level 
   whether a party has started.

	221 = deconnection : From its name with the code, this lets us 
   know that the client server has been disconnected.

	250 = move : This code lets the customer know that there is an
   entity entity performing a movement.

	257 = shoot : This code can be used to identify interactions between
   player and enemy interactions.

	530 = quit : This code, when sent, lets the customer know 
   to know that it must completely disconnect from the client.

	211 = left : This code allows us to identify that the entity 
   moves to the left.

   212 = right : This code allows us to identify that the entity 
   moves to the right.

	213 = up : This code allows us to identify that the entity 
   is moving upwards.

	214 = down : This code allows us to identify that the entity 
   is moving downwards.

	Once the server has received these different codes, it knows 
    exactly what action to execute. This ensures a smooth collision 
    between the different entities in the game.

## Reception at the server's

After sending these different codes, the server receives them and
      then goes on to process the retrieved information.

      With these codes, the waiter would know what to do with his
      level. And this is how it reacts to the different codes.

      When the server receives:
	500 : This tells the server that there has been a connection problem.

	230 : This code notifies the customer that the connection has been
     been established.

	332 : This tells the server that an entity has joined a player group 
     or a new game.

	201 : This enables the server to create the entities required 
     to generate a game.

    221 : When this code is sent to the server level, the latter 
     deletes the entities to end the game.

	250 : On seeing this code, the server increments the position 
     of the entity.

	257 : Once this code has been sent to the server, the latter 
     activates the entity responsible for managing in-game shooting
     events

	530 : The latter lets the server know that it's time to
     to break the connection with the client.

	211 : This allows the server to move the moving entity
     left on the abssice axis.

	212 : This allows the server to move the moving entity
     right on the abssice axis.

	213 : Cela permet au serveur déplacé l'entité en
     mouvement vers la haut sur l'axe de ordonné.

	214 : This allows the server to move the moving entity
     down the order axis.

     Finally, we need to understand that it's these different
     codes that server and client to communicate with each other.
     So we can quickly detect problems.

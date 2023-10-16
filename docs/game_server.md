### GameEngine::createPlayer

int GameEngine::createPlayer(int x, int y, int nb) noexcept

Description

This function is responsible for creating a player entity in the game. It creates and configures the necessary components for the player entity, such as draw, position, movement, and input.
Parameters

    * x (int): The initial x-coordinate of the player's position.
    * y (int): The initial y-coordinate of the player's position.
    * nb (int): The player number.

Return Value

    int: The index of the created player entity.

Example Usage

int playerIndex = gameEngine.createPlayer(100, 200, 1);

### GameEngine::createPlayerBullet

int GameEngine::createPlayerBullet(int x, int y, float damage, float speed, int dirX, int dirY, float size) noexcept

Description

This function is responsible for creating a player bullet entity in the game. It creates and configures the necessary components for the bullet entity.
Parameters

    * x (int): The initial x-coordinate of the bullet's position.
    * y (int): The initial y-coordinate of the bullet's position.
    * damage (float): The damage inflicted by the bullet.
    * speed (float): The speed of the bullet.
    * dirX (int): The x-direction of the bullet.
    * dirY (int): The y-direction of the bullet.
    * size (float): The size of the bullet.

Return Value

    int: The index of the created bullet entity.

Example Usage

int bulletIndex = gameEngine.createPlayerBullet(150, 300, 10.0f, 8.0f, 1, 0, 0.5f);

Please note that this documentation is generated based on the provided code snippet, and the actual functionality and usage of these functions may depend on the implementation details not provided in the code.
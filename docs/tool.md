## Shortcut Way

### Description

The Shortcut Way header file defines various shortcuts and paths used in the game. It includes definitions for sprite paths, audio paths, and a few constant strings.

### Macros

    * SPRITE(id):
        * Description: Macro for constructing the path of a sprite based on its ID.
        * Parameters:
            id (string): The ID of the sprite.
        * Example:

    std::string spritePath = SPRITE("enemy");

### AUDIO(name):

    * Description: Macro for constructing the path of an audio file based on its name.
    * Parameters:
        name (string): The name of the audio file.
    * Example:

        std::string audioPath = AUDIO("explosion.wav");

### Constants

    * EXPLOSION_PATH:
        * Description: The path of the explosion sound effect audio file.
        * Type: std::string
        * Example:

    std::string explosionPath = EXPLOSION_PATH;

### HEAL_PATH:

    * Description: The path of the heal sound effect audio file.
    * Type: std::string
    * Example:

    std::string healPath = HEAL_PATH;

### HURT_PATH:

    * Description: The path of the hurt sound effect audio file.
    * Type: std::string
    * Example:

    std::string hurtPath = HURT_PATH;

### MENU_PATH:

    * Description: The path of the menu sound effect audio file.
    * Type: std::string
    * Example:

    std::string menuPath = MENU_PATH;

### PIOU_PATH:

    * Description: The path of the piou sound effect audio file.
    * Type: std::string
    * Example:

    std::string piouPath = PIOU_PATH;

### POWERUP_PATH:

    * Description: The path of the power-up sound effect audio file.
    * Type: std::string
    * Example:

    std::string powerUpPath = POWERUP_PATH;

### MUSIC_BG_PATH:

    * Description: The path of the background music audio file.
    * Type: std::string
    * Example:

        std::string musicBgPath = MUSIC_BG_PATH;

## Touch
### Description

The Touch enumeration defines various touch inputs available in the game. It represents different key inputs or touch gestures that can be used for interaction.
### Enumerators

    * None to Exit:
        * Description: Touch enumerators representing different touch inputs.
        * Type: Touch
        * Example:

        Touch touchInput = Touch::Left;

Please note that this documentation is generated based on the provided code snippets, and the actual functionality and usage of these definitions may depend on the implementation details not provided in the code.
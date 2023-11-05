# Serializer Documentation

***Description***

The Serializer class provides methods for serializing data into a vector of bytes. It includes methods for serializing entity components, music components, and key codes.

## Header File

```cpp
#include "../../include/Serializer/Serializer.hpp"
```

## Public Methods

### RawData serialize(std::unique_ptr\<Entity\> const& entity, std::vector\<Player\> players_) noexcept

Serializes the position and drawable components of an entity into a vector of bytes.

**Parameters:**

- `entity`: A unique pointer to the entity to be serialized.
- `players_`: A vector of players.

**Return Value:**

- A vector of uint8_t representing the serialized data.

### RawData serializeMusic(std::unique_ptr\<Entity\> const& entity) noexcept

Serializes the sound component of an entity into a vector of bytes.

**Parameters:**

- `entity`: A unique pointer to the entity to be serialized.

**Return Value:**

- A vector of uint8_t representing the serialized data.

### RawData serialize(int keyCode)

Serializes an integer into a vector of bytes.

**Parameters:**

- `keyCode`: The key code to be serialized.

**Return Value:**

- A vector of uint8_t representing the serialized data.

### Example Usage

```cpp
#include "../../include/Serializer/Serializer.hpp"

int main()
{
    Serializer serializer;
    std::unique_ptr<Entity> entity = std::make_unique<Entity>();

    // Serialize entity components
    RawData serializedData = serializer.serialize(entity, players_);

    // Serialize music component
    RawData musicData = serializer.serializeMusic(entity);

    // Serialize key code
    RawData keyCodeData = serializer.serialize(65);

    return 0;
}
```

Note: The above example assumes that the necessary header files and libraries are included and linked properly, and that the `players_` vector and the `Entity` object are properly defined and initialized.
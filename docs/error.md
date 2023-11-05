# Error Documentation

## Error Class

### Description

The Error class is used to represent an error condition in the program. It provides a mechanism for storing and retrieving an error message.

### Header File

```cpp
#include "../../include/Error/Error.hpp"
```

### Constructors

#### Error(std::string message) noexcept

Constructs an Error object with the specified error message.

**Parameters:**

- `message`: The error message to be displayed.

### Public Methods

#### const char* what() const noexcept

Returns a pointer to a C-style string that contains the error message.

### Example Usage

```cpp
#include "../../include/Error/Error.hpp"

int main()
{
    try
    {
        throw Error("An error occurred");
    }
    catch (const Error& e)
    {
        std::cout << "Error message: " << e.what() << std::endl;
    }

    return 0;
}
```

## InitError Class

### Description

The InitError class is a derived class of the Error class. It represents an error condition that occurs during initialization.

### Constructors

#### InitError(std::string message) noexcept

Constructs an InitError object with the specified error message.

**Parameters:**

- `message`: The error message to be displayed.

### Example Usage

```cpp
#include "../../include/Error/Error.hpp"

int main()
{
    try
    {
        throw InitError("Initialization failed");
    }
    catch (const Error& e)
    {
        std::cout << "Error message: " << e.what() << std::endl;
    }

    return 0;
}
```

## NetworkError Class

### Description

The NetworkError class is a derived class of the Error class. It represents an error condition that occurs during network operations.

### Constructors

#### NetworkError(std::string message) noexcept

Constructs a NetworkError object with the specified error message.

**Parameters:**

- `message`: The error message to be displayed.

### Example Usage

```cpp
#include "../../include/Error/Error.hpp"

int main()
{
    try
    {
        throw NetworkError("Network error occurred");
    }
    catch (const Error& e)
    {
        std::cout << "Error message: " << e.what() << std::endl;
    }

    return 0;
}
```

Note: The above examples assume that the necessary header files and libraries are included and linked properly.
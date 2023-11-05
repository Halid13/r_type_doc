# JsonTools Documentation

***Description***

The JsonTools class provides methods for working with JSON files and objects. It includes a method for reading a JSON file and returning the JSON object.

## Header File

```cpp
#include "../../include/Json/JsonTools.hpp"
```

## Public Methods

**json getPatternsFromFile()**

Reads a JSON file and returns the JSON object.

**Parameters:**

- None

**Return Value:**

- A JSON object representing the contents of the file.

### Example Usage

```cpp
#include "../../include/Json/JsonTools.hpp"

int main()
{
    JsonTools jsonTools;

    // Read a JSON file and get the JSON object
    json patterns = jsonTools.getPatternsFromFile();

    // Print the JSON object
    std::cout << patterns.dump(4) << std::endl;

    return 0;
}
```

Note: The above example assumes that the necessary header files and libraries are included and linked properly, and that the JSON file exists at the specified path.
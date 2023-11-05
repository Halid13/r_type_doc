# ComponentBehavior

***Description***

The `ComponentBehavior` class is a derived class of `IComponent` and represents the behavior component of an entity. It provides functionality for updating the entity's behavior.

***Public Members***

- `ComponentBehavior()`: Default constructor.
- `~ComponentBehavior()`: Default destructor.
- `void setupdate(std::function<void(Entity* entity)> update)`: Sets the update function for the component.
- `void Update(Entity* entity)`: Updates the behavior of the entity.

***Private Members***

- `std::function<void(Entity* self)> _update_`: Function object representing the update function for the component.

---

# ComponentDraw

***Description***

The `ComponentDraw` class is a derived class of `IComponent` and represents the drawing component of an entity. It provides functionality for managing the position, size, scale, and texture ID of the entity's sprite.

***Public Members***

- `ComponentDraw(int X, int Y, int width, int height, int textureId)`: Constructor that initializes the drawing component with the specified position, size, and texture ID.
- `~ComponentDraw()`: Destructor.
- `std::tuple<int, int> getX_Y() noexcept`: Returns the X and Y coordinates of the drawing component.
- `std::tuple<int, int> getHeightandWidth() noexcept`: Returns the height and width of the drawing component.
- `std::tuple<double, double> getScaleX_Y() noexcept`: Returns the X and Y scale factors of the drawing component.
- `int getTextureId() noexcept`: Returns the texture ID of the drawing component.
- `void setWidth(int width) noexcept`: Sets the width of the drawing component.
- `void setHeight(int height) noexcept`: Sets the height of the drawing component.
- `void setScale(float x, float y) noexcept`: Sets the X and Y scale factors of the drawing component.
- `void setTextureId(int textureId) noexcept`: Sets the texture ID of the drawing component.
- `Sprite& getSprite() noexcept`: Returns a reference to the sprite associated with the drawing component.

***Private Members***

- `int _X`: The X coordinate of the drawing component.
- `int _Y`: The Y coordinate of the drawing component.
- `int _width`: The width of the drawing component.
- `int _heigth`: The height of the drawing component.
- `int _textureId`: The texture ID of the drawing component.
- `double _scaleX`: The X scale factor of the drawing component.
- `double _scaleY`: The Y scale factor of the drawing component.
- `Sprite sprite_`: The sprite associated with the drawing component.

---

# ComponentInput

***Description***

The `ComponentInput` class is a derived class of `IComponent` and represents the input component of an entity. It provides functionality for managing input values associated with the entity.

***Public Members***

- `ComponentInput()`: Default constructor.
- `~ComponentInput()`: Default destructor.
- `void addInput(int input) noexcept`: Adds an input value to the component.
- `int getInput() noexcept`: Returns the input value associated with the component.

***Private Members***

- `std::vector<int> _input`: A vector storing the input values associated with the component.

---

# ComponentMouvement

***Description***

The `ComponentMouvement` class is a derived class of `IComponent` and represents the movement component of an entity. It provides functionality for managing the position and speed of the entity.

***Public Members***

- `ComponentMouvement(int X, int Y, double speed)`: Constructor that initializes the movement component with the specified position and speed.
- `~ComponentMouvement()`: Destructor.
- `std::tuple<int, int> getXandY() noexcept`: Returns the X and Y coordinates of the movement component.
- `double getSpeed() noexcept`: Returns the speed of the movement component.
- `void setX(int X) noexcept`: Sets the X coordinate of the movement component.
- `void setY(int Y) noexcept`: Sets the Y coordinate of the movement component.
- `void setSpeed(double speed) noexcept`: Sets the speed of the movement component.

***Private Members***

- `int _X`: The X coordinate of the movement component.
- `int _Y`: The Y coordinate of the movement component.
- `double _speed`: The speed of the movement component.

---

# ComponentPosition

***Description***

The `ComponentPosition` class is a derived class of `IComponent` and represents the position component of an entity. It provides functionality for managing the position of the entity.

***Public Members***

- `ComponentPosition(int x, int y) noexcept`: Constructor that initializes the position component with the specified coordinates.
- `~ComponentPosition() noexcept`: Destructor.
- `std::tuple<int, int> getXandY() const noexcept`: Returns the X and Y coordinates of the position component.
- `void setXandY(int x, int y) noexcept`: Sets the X and Y coordinates of the position component.

***Protected Members***

- `int _x`: The X coordinate of the position component.
- `int _y`: The Y coordinate of the position component.

---

Please note that this documentation is based on the provided code snippets and may not cover all the details or context of the entire system. It is recommended to refer to the actual code implementation and any associated comments for a complete understanding.
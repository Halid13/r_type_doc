# Entity

***Description***

The `Entity` class represents an entity in a game or simulation. It is a container for components that define the properties and behaviors of the entity. Each entity has a unique identifier.

***Public Members***

- `Entity(size_t id) noexcept`: Constructor that creates an entity with the specified identifier.
- `~Entity() noexcept`: Destructor.
- `size_t getIdex() noexcept`: Returns the identifier of the entity.
- `std::vector<std::shared_ptr<IComponent>>& getEntityComponent() noexcept`: Returns a reference to the vector of components associated with the entity.
- `template <typename T> void addComponent(T& component) noexcept`: Adds a component of type `T` to the entity.
- `template <typename T> T* getComponent() noexcept`: Returns a pointer to the component of type `T` associated with the entity.
- `template <typename T> int EntityhaveComponent() noexcept`: Checks if the entity has a component of type `T`.
- `template <typename T, typename... Args> bool hasComponents() noexcept`: Checks if the entity has components of types `T` and `Args...`.

***Private Members***

- `std::vector<std::shared_ptr<IComponent>> _component`: A vector of shared pointers to the components associated with the entity.
- `size_t _id`: The identifier of the entity.

---

# EntityManager

***Description***

The `EntityManager` class manages a collection of entities. It provides functionality for creating, accessing, and removing entities.

***Public Members***

- `EntityManager() noexcept`: Default constructor.
- `~EntityManager() noexcept`: Destructor.
- `std::shared_ptr<Entity> CreateEntity() noexcept`: Creates a new entity and returns a shared pointer to it.
- `std::vector<std::shared_ptr<Entity>>& getEntity() noexcept`: Returns a reference to the vector of entities managed by the entity manager.
- `std::shared_ptr<Entity> findEntity(size_t id) noexcept`: Finds an entity with the specified identifier and returns a shared pointer to it.
- `int eraseEntity(size_t id) noexcept`: Removes an entity with the specified identifier from the entity manager.

***Private Members***

- `std::vector<std::shared_ptr<Entity>> _entity`: A vector of shared pointers to the entities managed by the entity manager.

---

Please note that this documentation is based on the provided code snippets and may not cover all the details or context of the entire system. It is recommended to refer to the actual code implementation and any associated comments for a complete understanding.
# Pure Fabrication

**Definition:** Assign a highly cohesive set of responsibilities to an artificial class that does not represent a concept in the problem domain, particularly to support high cohesion, low coupling, and reuse.

**Example:** Introducing a `Logger` class to handle logging, which doesn't naturally fit into the domain model but is necessary for cross-cutting concerns.

```cpp
class Logger {
public:
    static void log(const std::string& message) {
        // Implementation for logging messages
    }
};
```

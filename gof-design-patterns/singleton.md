# Singleton

### Type of Pattern

Creational

### Problem at Hand

The need to ensure that a class has only one instance and provides a global point of access to that instance. This is particularly useful when exactly one object is needed to coordinate actions across the system.

### Solution

The Singleton pattern solves this problem by:

* Making the class's constructor private to prevent external instantiation.
* Creating a static method that acts as a constructor. This method calls the constructor to create an instance if one doesn't exist and returns the instance if it does.

### Example

A classic example of the Singleton pattern is a database connection manager class. In many applications, it's desirable to have a single point of access to the database to avoid the overhead of opening and closing connections multiple times.

```java
public class Database {
    private static Database instance;

    private Database() {
        // private constructor to prevent instantiation
    }

    public static Database getInstance() {
        if (instance == null) {
            instance = new Database();
        }
        return instance;
    }

    public void query(String sql) {
        // method to query the database
    }
}
```

### Components of the Design

* **Private constructor**: Ensures that instances cannot be created from outside the class.
* **Static instance variable**: Holds the singleton instance.
* **Public static method**: This is the global access point to the instance.

### Subcategories/Types

There are a few variations to the Singleton pattern, such as:

* **Lazy instantiation**: The instance is created when it is first requested.
* **Eager instantiation**: The instance is created as soon as the class is loaded.
* **Thread-safe Singleton**: Ensures that the Singleton instance is created safely in a multithreaded environment.

### Drawbacks

* **Global state**: Singleton can hide dependencies instead of exposing them through interfaces, making the system harder to understand.
* **Testing**: It can be more difficult to test the clients of a Singleton because it's hard to replace a Singleton with a mock object.
* **Scalability**: Since there is only one instance, scaling the application might be limited in scenarios where instance-specific state is desired.

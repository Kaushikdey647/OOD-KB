---
description: General Responsibility Assignment Software Patterns
---

# GRASP

GRASP (General Responsibility Assignment Software Patterns) are a set of principles aimed at solving common problems in the design of object-oriented software. These patterns provide guidelines for assigning responsibilities to classes and objects in a way that leads to a robust, maintainable, and modular design. The core idea is to increase cohesion and reduce coupling among components, making the system easier to understand, develop, and change.

Certainly, Kaushik. Let's delve into each of these GRASP (General Responsibility Assignment Software Patterns) with examples in C++ to illustrate their application and benefits.

### 1. Expert

**Definition:** Assign a responsibility to the class that has the information necessary to fulfill it.

**Example:** If we're implementing a shopping cart, the `CartItem` class should be responsible for calculating its own total cost because it holds the necessary information (price, quantity).

```cpp
class CartItem {
public:
    CartItem(double price, int quantity) : price(price), quantity(quantity) {}
    double calculateTotal() const {
        return price * quantity;
    }
private:
    double price;
    int quantity;
};
```

### 2. Creator

**Definition:** Assign class B the responsibility to create an instance of class A if one (or more) of the following is true: B aggregates A, B contains A, B records A, B closely uses A, B has the initializing data for A.

**Example:** If a `ShoppingCart` contains `CartItem` objects, it makes sense for `ShoppingCart` to be responsible for creating `CartItem` instances.

```cpp
class ShoppingCart {
public:
    void addItem(double price, int quantity) {
        items.push_back(CartItem(price, quantity));
    }
private:
    std::vector<CartItem> items;
};
```

### 3. Controller

**Definition:** Assign the responsibility of handling a system event to a class representing one of the following choices: represents the overall system or a use case scenario within which the system event occurs.

**Example:** A `ShoppingCartController` can handle requests related to the shopping cart, acting as an intermediary between the view (UI) and the model (`ShoppingCart`).

```cpp
class ShoppingCartController {
public:
    void addItemToCart(double price, int quantity) {
        cart.addItem(price, quantity);
    }
private:
    ShoppingCart cart;
};
```

### 4. Pure Fabrication

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

### 5. Indirection

**Definition:** Assign the responsibility to an intermediate object to mediate between other components or services so as to decouple them from each other.

**Example:** Using a `PaymentServiceInterface` as an intermediary between the `ShoppingCart` and various payment implementations (`CreditCardPayment`, `PaypalPayment`) to decouple the shopping cart from specific payment methods.

```cpp
class PaymentServiceInterface {
public:
    virtual void pay(double amount) = 0;
};

class CreditCardPayment : public PaymentServiceInterface {
public:
    void pay(double amount) override {
        // Credit card payment implementation
    }
};

class ShoppingCart {
public:
    void checkout(PaymentServiceInterface& paymentService) {
        double totalAmount = calculateTotal();
        paymentService.pay(totalAmount);
    }
private:
    double calculateTotal() {
        // Calculate total amount
        return 100.0; // Example amount
    }
};
```

Each pattern offers a strategic solution for assigning responsibilities in object-oriented design, aiming for a design that is more maintainable, understandable, and decoupled.

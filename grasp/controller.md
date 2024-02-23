# Controller

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

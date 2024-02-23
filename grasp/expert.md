# Expert

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

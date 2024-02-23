# Creator

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

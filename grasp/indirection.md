# Indirection

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

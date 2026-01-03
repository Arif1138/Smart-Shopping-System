# 🛒 E-Commerce Smart Cart System

A Java-based shopping cart simulation demonstrating core **Object-Oriented Programming (OOP)** principles, specifically **Inheritance**, **Polymorphism**, and **Dynamic List Management**.

## 🚀 Project Overview
This project simulates a backend logic for an e-commerce store where different types of products (e.g., Technology, Clothing) share common attributes but behave differently regarding price calculations (taxes, discounts). Unlike traditional static array implementations, this project utilizes `ArrayList` for dynamic inventory management.

## 🛠 Key Features & Concepts
* **Inheritance:** A base `Product` class is extended by `Technology` and `Clothing` subclasses to share common fields like `name` and `price`.
* **Polymorphism:** The `calculatePrice()` method is overridden in subclasses to apply specific logic (e.g., adding tax to electronics or applying seasonal discounts to clothing) dynamically at runtime.
* **Dynamic Collections:** Uses `Java ArrayList` instead of fixed-size arrays to manage the shopping cart, allowing for flexible product additions without manual resizing logic.
* **Encapsulation:** Proper use of private fields, getters/setters, and constructors to ensure data integrity.
* **Super Keyword:** Efficiently initializes parent class attributes from child constructors using `super()`.

## 📂 Class Structure
* **`Product` (Parent):** Base entity representing a generic item with a name and raw price.
* **`Technology` (Child):** Extends `Product`. Adds attributes like `brand` and `hasWarranty`. It overrides `calculatePrice` to include a tax rate.
* **`Clothing` (Child):** Extends `Product`. Adds attributes like `size` and `material`. It overrides `calculatePrice` to apply a discount.
* **`ShoppingCart`:** Manages the list of products using `ArrayList<Product>` and calculates the total cart cost using a polymorphic loop.

## 💻 Usage Example

```java
public static void main(String[] args) {
    ShoppingCart cart = new ShoppingCart();

    // Polymorphism in action: Adding different subclasses to the same list
    Product laptop = new Technology("Gaming Laptop", 1500.0, "BrandX", true);
    Product tShirt = new Clothing("Cotton T-Shirt", 20.0, "L", "Cotton");

    cart.addProduct(laptop); // Automatically calculates tax
    cart.addProduct(tShirt); // Automatically applies discount

    System.out.println("Total Cart Amount: " + cart.calculateTotal());
}

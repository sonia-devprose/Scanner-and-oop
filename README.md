## Comprehensive Java Documentation: Scanner with OOP Principles

To use the `Scanner` class, you must first import it from the Java utility library. This documentation will take you from a basic implementation to a professional, robust structure.

### 1. The Essential Import

At the very top of your `.java` file (before your class definition), you must include:

```java
import java.util.Scanner;

```

---

### 2. Basic Example: Direct Input to Object

In this basic scenario, we use a **Constructor** to immediately assign user input to an object.

#### The "User" Class

```java
public class User {
    private String username;

    // Constructor
    public User(String username) {
        this.username = username;
    }

    // Getter
    public String getUsername() {
        return username;
    }
}

```

#### The Main Implementation

```java
Scanner sc = new Scanner(System.in);

System.out.print("Enter your username: ");
String inputName = sc.nextLine();

// Using the constructor to set the value immediately
User myUser = new User(inputName);

System.out.println("User created: " + myUser.getUsername());

```

---

### 3. Complex Example: The "Interactive Profile"

In a more complex application, you often create an object first and use **Setters** to update it as the user navigates a menu or provides more data. This example also handles the common "Buffer Bug" where numbers interfere with text input.

#### The "Product" Class

```java
public class Product {
    private String name;
    private double price;
    private int stock;

    // Default Constructor
    public Product() {}

    // Setters
    public void setName(String name) { this.name = name; }
    public void setPrice(double price) { this.price = price; }
    public void setStock(int stock) { this.stock = stock; }

    // Getters
    public String getName() { return name; }
    public double getPrice() { return price; }
}

```

#### The Advanced Logic

```java
Scanner sc = new Scanner(System.in);
Product laptop = new Product();

System.out.println("--- Product Entry System ---");

System.out.print("Enter Product Name: ");
laptop.setName(sc.nextLine());

System.out.print("Enter Price: ");
double p = sc.nextDouble();
laptop.setPrice(p);

// CRITICAL: Clear the buffer after nextDouble() 
// so the next nextLine() doesn't get skipped!
sc.nextLine(); 

System.out.print("Enter Category: ");
String cat = sc.nextLine(); 

System.out.println("\nSuccess: " + laptop.getName() + " costs $" + laptop.getPrice());

```

---

### 4. Final Documentation Summary

| Step | Action | Code Snippet |
| --- | --- | --- |
| **1. Import** | Bring the tool into your file. | `import java.util.Scanner;` |
| **2. Initialize** | Create the scanner instance. | `Scanner sc = new Scanner(System.in);` |
| **3. Capture** | Store input in a temporary variable. | `String data = sc.nextLine();` |
| **4. Assign** | Pass variable to Object via Constructor/Setter. | `obj.setName(data);` |
| **5. Retrieve** | Use Getter to display or use the data. | `obj.getName();` |

> **Best Practice:** Always close your scanner at the very end of your `main` method using `sc.close();` to prevent memory leaks, though for simple console apps, Java handles this gracefully.

Would you like me to create a "Menu-Driven" example where the user can choose to Update, View, or Exit using a `while` loop?

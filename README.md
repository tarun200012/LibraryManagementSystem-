# LibraryManagementSystem-

# 📚 Library Management System (Java Console App)

A simple Java console-based Library Management System demonstrating **OOP**, **SOLID principles**, and **Design Patterns**. It allows users to manage books, patrons, and lending through a command-line interface.

---

## ✨ Features

- ✅ Add, update, delete, and search books
- ✅ Register and manage patrons
- ✅ Checkout and return books
- ✅ Track available and borrowed books
- ✅ Console-based user interaction
- ✅ Logs key actions and errors

---

## 💡 Object-Oriented Design

This system uses core OOP principles:

| Principle       | Applied |
|----------------|---------|
| Encapsulation  | ✅       |
| Abstraction    | ✅       |
| Inheritance    | ⚠️ (Ready for future) |
| Polymorphism   | ✅       |

---

## 🔐 SOLID Principles

| Principle                    | Usage Example |
|-----------------------------|-----------------------------|
| Single Responsibility        | Each service (Book, Patron, Lending) has one job |
| Open/Closed                  | Easily add new features without changing old code |
| Liskov Substitution          | Prepared for with expandable models (e.g. Patron → PremiumPatron) |
| Interface Segregation        | Ready for interface segregation in future (e.g. Searchable) |
| Dependency Inversion         | Constructor-based injection used in services |

---

## 🧠 Design Patterns

- **Factory Pattern** – used to create `Book` and `Patron` objects.
- (Optional) **Observer Pattern** – can be added for reservation notifications.

---

**Class Diagram**

     +-----------------------+
                           |   LibraryApplication  |
                           +-----------------------+
                             |     |     |     |
                             v     v     v     v
               +----------------+  +-----------------+  +------------------+  +---------------------+
               |  BookManager   |  | PatronManager   |  | LendingService   |  | InventoryService    |
               +----------------+  +-----------------+  +------------------+  +---------------------+
                       |                   |                |     |                    |
                       v                   v                +-----+                    |
                +-------------+      +-------------+         Uses                     Uses
                |    Book     |      |   Patron    |     BookManager &          BookManager
                +-------------+      +-------------+     PatronManager          to check status
                | - title     |      | - patronId  |                              of books
                | - author    |      | - name      |
                | - isbn      |      | - borrowingHistory: List<Book> |
                | - year      |      
                | - isBorrowed|      

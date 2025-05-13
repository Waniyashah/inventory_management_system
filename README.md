# Inventory Management System – Project Summary
The Inventory Management System is a console-based application designed to streamline the management of various types of products in a store. It enables the user to add, sell, search, and remove products while maintaining accurate stock levels. The system is built using core Object-Oriented Programming (OOP) principles, ensuring a modular, reusable, and easily maintainable codebase.

# System Architecture and Mechanism
# Product Hierarchy (Abstraction & Inheritance)
At the heart of the system is the Product abstract base class, which serves as a blueprint for all product types. It defines essential attributes such as:
product_id
name
price
quantity_in_stock
It also provides shared functionality, including:
restock()
sell()
get_total_value()

# Three specialized product classes inherit from this base:
Electronics: Includes warranty_years and brand
Grocery: Includes expiry_date and is_expired() method
Clothing: Includes size and material

Each subclass overrides the abstract methods (__str__, to_dict, from_dict) to provide product-specific representations and data handling.

# Encapsulation
The system uses encapsulation to protect internal state and validate input through:

Private/protected attributes (e.g., _price, _name)

Property decorators (@property, @setter) to control access and enforce constraints, such as ensuring that prices and quantities are positive.

# Polymorphism
Polymorphism allows the system to interact with all product types uniformly. For example, the Inventory class can store different product types in a single collection and call common methods (__str__, to_dict) on them without needing to know their specific class.

# Exception Handling
Custom exception classes improve the robustness of the system:
InsufficientStockError: Raised when attempting to sell more items than available
DuplicateProductError: Raised when trying to add a product with an existing ID
InvalidProductDataError: Raised when loading malformed or invalid data from file

These exceptions provide clear feedback to the user and prevent system crashes.

# Inventory Class (Controller)
This class is responsible for managing all product operations. It maintains a dictionary of products and provides methods to:
Add and remove products
Sell and restock items
Search products by name or type
Remove expired grocery items
Calculate total inventory value
Save/load product data to/from JSON files

# InventoryCLI (User Interface Layer)
This component provides a command-line interface for interacting with the system. It presents the user with a menu of options and captures input to perform actions like:
Adding new products
Viewing or searching inventory
Selling items
Removing expired groceries
Saving and loading inventory data

# Key Object-Oriented Concepts Applied
Concept	Application
Abstraction	The Product abstract class defines common behavior for all products
Encapsulation	Properties and setters control access and validation of attributes
Inheritance	Electronics, Grocery, and Clothing extend the Product base class
Polymorphism	Shared methods (__str__, to_dict) behave differently depending on the class

# Conclusion
This Inventory Management System demonstrates a well-structured application of object-oriented principles. By separating concerns across multiple classes, utilizing abstraction and inheritance, and ensuring data integrity through encapsulation and exception handling, the system provides a flexible, scalable, and maintainable solution for managing product inventories.

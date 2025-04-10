# 🛒 E-Commerce Website

This is a PHP-based e-commerce platform designed to provide core shopping functionality for **customers** and **management tools** for **admins**. It includes user registration, login, shopping cart, and product management features.

---

## 📁 Project Structure

- `index.php` — Homepage displaying all products.
- `register.php` — User registration page.
- `login.php` / `logout.php` — User authentication pages.
- `cart.php` — User shopping cart page.
- `admin/` — Admin panel for managing products and inventory.

---

## 👥 1. User Section

### 1.1. Registering on the Platform
Users can register via `register.php` by entering:
- Name
- Email
- Password  
Their information is saved securely in the database.

### 1.2. Login & Logout
- **Login:** `login.php` — Users enter email and password.
- **Logout:** `logout.php` — Ends the user session.

### 1.3. Browsing Products
All available products are shown on the homepage (`index.php`) with:
- Name
- Price
- Description
- Product image

### 1.4. Adding Products to Cart
Clicking the **"Add to Cart"** button on a product in `index.php` saves the item to the cart for the logged-in user.

### 1.5. Managing the Cart
In `cart.php`, users can:
- View cart items
- Change quantity
- Remove items  
The total cost is calculated dynamically.

---

## 🔐 2. Admin Section

### 2.1. Admin Login & Logout
- **Login:** `admin/login.php`
- **Logout:** `admin/logout.php`  
Only users with the **admin** role can log in.

### 2.2. Admin Dashboard
- `admin/dashboard.php` — Control panel to manage the store.

### 2.3. Adding Products
- `admin/add_product.php` — Admins add products by entering details and uploading images.

### 2.4. Managing Products
- `admin/manage_products.php` — Admins can:
  - View all products
  - Edit product details
  - Delete products

---

## 🗄️ 3. Database Structure

### 3.1. `users` Table
Stores user details:
- `id`, `name`, `email`, `password` (hashed), `role` (`user` or `admin`)

### 3.2. `products` Table
Holds product data:
- `id`, `name`, `price`, `description`, `image`

### 3.3. `cart` Table
Tracks cart items:
- `id`, `user_id`, `product_id`, `quantity`

---

## 🔄 4. Flow of the Website

### 4.1. User Registration
- Validates input
- Hashes password using `password_hash()`
- Stores data in the `users` table

### 4.2. User Login
- Verifies credentials
- Starts a session with `$_SESSION['user_id']`

### 4.3. Adding Items to Cart
- Saves product ID and quantity in the `cart` table associated with the user

### 4.4. Admin Adding Products
- Uploads image
- Saves details to the `products` table
- Product appears on homepage

### 4.5. Admin Deleting Products
- Removes product from `products` table
- Product is no longer visible to users

---

## 🔐 5. Security Measures

### 5.1. Password Security
- Passwords are hashed using `password_hash()` before storage.

### 5.2. Session Management
- PHP sessions handle login status:
  - `$_SESSION['user_id']` for customers
  - `$_SESSION['admin_id']` for admins

### 5.3. Admin Access
- Admin pages check the `role` field from the `users` table to block unauthorized access.

---

## 🚀 How to Use This Guide

- Follow each section to understand how the site operates.
- Refer to the corresponding PHP files for implementation details.
- Use this as a base to expand features like:
  - Order checkout
  - Payment integration
  - Product categories
  - Search functionality

---

## 🧑‍💻 Technologies Used

- PHP
- MySQL
- HTML/CSS
- JavaScript (optional for interactivity)
- Apache (recommended via XAMPP or similar)

---

## ✅ Setup Instructions

1. **Clone or download** the project files.
2. **Set up the database** using the provided `.sql` file (if available).
3. **Configure database connection** in a config file (e.g., `config.php`).
4. **Run the project** in a local server environment like XAMPP.

---

## 📩 Feedback & Contributions

Feel free to open issues or submit pull requests if you'd like to contribute or improve this project!

---

**Author:** *Pallerla Sohan *  
**License:** This project is licensed under the MIT License

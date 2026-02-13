# SmartCart

SmartCart is a feature-rich e-commerce web application built with **Flask** (Python) and **MySQL**. It features separate administrative and user interfaces, secure authentication, product management, shopping cart functionality, and Razorpay payment integration.

## Features

### Admin Panel
*   **Secure Authentication**: Admin signup with OTP verification and secure login.
*   **Product Management**: Add, update, view, and delete products. Includes image upload.
*   **Dashboard**: Overview of products with search and category filtering.
*   **Order Management**: View all customer orders and update order status (e.g., shipped, delivered).
*   **Profile Management**: Update admin details and profile picture.

### User Panel
*   **User Account**: Signup with OTP verification and login.
*   **Browse Products**: View products by category and search functionality.
*   **Shopping Cart**: Add items, adjust quantities, and remove items.
*   **Checkout**: Integrated **Razorpay** payment gateway for secure transactions.
*   **Order History**: View past orders and status.
*   **Invoicing**: Auto-generated PDF invoices for orders.

## Tech Stack

*   **Backend**: Python, Flask
*   **Database**: MySQL
*   **Frontend**: HTML, CSS, Bootstrap, JavaScript
*   **Authentication**: Flask-Login / Session-based, Bcrypt for hashing
*   **Utilities**: Flask-Mail (OTP/Notifications), WeasyPrint (PDF Invoice)

## Prerequisites

Ensure you have the following installed:
*   [Python 3.x](https://www.python.org/)
*   [MySQL Server](https://dev.mysql.com/downloads/installer/)
*   [Git](https://git-scm.com/)

## Installation

1.  **Clone the Repository**
    ```bash
    git clone https://github.com/Kotlasatya/SmartCart.git
    cd SmartCart
    ```

2.  **Create and Activate Virtual Environment**
    ```bash
    python -m venv venv
    # Windows
    venv\Scripts\activate
    # Mac/Linux
    source venv/bin/activate
    ```

3.  **Install Dependencies**
    ```bash
    pip install -r requirements.txt
    ```
    *Note: If `requirements.txt` is missing specific packages, ensure you have basic Flask packages installed (`flask`, `mysql-connector-python`, `flask-mail`, `flask-bcrypt`, `razorpay`, `weasyprint`).*

4.  **Database Setup**
    *   Open your MySQL Client (Workbench or Command Line).
    *   Create the database and tables using the provided schema file:
    ```sql
    source database/schema.sql;
    ```
    *Alternatively, copy the SQL commands from `database/schema.sql` and run them manually.*

5.  **Configuration**
    *   Open `config.py`.
    *   Update the specific configurations to match your local setup:
        ```python
        # MySQL Database Configuration
        DB_HOST = "localhost"
        DB_USER = "your_mysql_user"      # e.g., root
        DB_PASSWORD = "your_mysql_password"
        DB_NAME = "smartcart_db"

        # Email SMTP Settings (For OTPs)
        MAIL_USERNAME = 'your_email@gmail.com'
        MAIL_PASSWORD = 'your_app_password' # Use App Password for Gmail
        ```

## Running the Application

1.  Start the Flask server:
    ```bash
    python app.py
    ```

2.  Open your browser and navigate to:
    *   **Home**: `http://127.0.0.1:5000/`
    *   **Admin Login**: `http://127.0.0.1:5000/admin-login`
    *   **User Login**: `http://127.0.0.1:5000/user-login`

## Project Structure

```
SmartCart/
├── app.py                  # Main application entry point & routes
├── config.py               # Configuration settings (DB, Mail, Keys)
├── requirements.txt        # Python dependencies
├── database/
│   └── schema.sql          # Database creation script
├── static/                 # CSS, Images, Uploads
│   ├── uploads/            # Product/Profile images
│   └── css/                # Stylesheets
├── templates/              # HTML Templates
│   ├── admin/              # Admin pages
│   ├── user/               # User pages
│   └── index.html          # Landing page
└── utils/                  # Helper functions (e.g., PDF generator)
```

## Contributing

1.  Fork the repository.
2.  Create your feature branch (`git checkout -b feature/AmazingFeature`).
3.  Commit your changes (`git commit -m 'Add some AmazingFeature'`).
4.  Push to the branch (`git push origin feature/AmazingFeature`).
5.  Open a Pull Request.

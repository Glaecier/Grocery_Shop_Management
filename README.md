# Grocery Shop Management System

A command-line inventory and sales management system for grocery stores, built with Python and MySQL. Features separate interfaces for shop owners and customers with real-time inventory tracking.

## Features

### Owner Functions
- **Add Products**: Register new products with ID, name, price, and quantity
- **Update Inventory**: Modify product quantities in stock
- **Delete Products**: Remove products from the inventory
- **View Inventory**: Display complete stock information

### Customer Functions
- **Browse Products**: View available products with prices and quantities
- **Purchase Items**: Buy multiple products in a single transaction
- **Generate Bills**: Automatic bill calculation with itemized receipts
- **Customer Records**: Store customer information for future reference

## Key Capabilities

- Real-time inventory updates after each purchase
- Input validation for all user entries
- Duplicate product ID prevention
- Stock availability checking
- Automated bill generation with customer details
- Typing animation effect for enhanced user experience

## Prerequisites

- Python 3.x
- MySQL Server
- MySQL Connector for Python

## Installation

1. Clone the repository:
```bash
git clone https://github.com/Glaecier/Grocery_Shop_Management.git
cd grocery-shop-management
```

2. Install required packages:
```bash
pip install mysql-connector-python
```

3. Set up MySQL database:
```sql
CREATE DATABASE trial_code;
```

4. Update database credentials in the code:
```python
self.db_connection = mysql.connector.connect(
    host="localhost",
    user="your_username",      # Change this
    password="your_password",  # Change this
    database="trial_code"
)
```

## Usage

Run the program:
```bash
python grocery_shop.py
```

### Menu Options

```
1. Add product          
2. Update quantity       
3. Delete product       
4. Display inventory     
5. Display products      
6. Buy products        
7. Exit                
```

### Customer Purchase Flow

1. Enter a 10-digit customer number
2. Provide name and email address
3. Select products by ID
4. Specify quantities
5. Receive itemized bill with total cost

## Input Validation

The system validates:
- Product IDs (must be unique, non-negative integers)
- Prices (non-negative numbers)
- Quantities (non-negative integers)
- Product names (alphabetic characters)
- Customer phone numbers (10-digit format)
- Email addresses (common domains: gmail.com, outlook.com, yahoo.com, hotmail.com, rediffmail.com)

## Database Schema

### Products Table
- `id` (INT, PRIMARY KEY)
- `name` (VARCHAR)
- `price` (FLOAT)
- `quantity` (INT)

### Customers Table
- `number` (BIGINT, PRIMARY KEY)
- `name` (VARCHAR)
- `email` (VARCHAR)

## Sample Workflow

**Adding a Product:**
```
Enter product ID: 101
Enter product name: Apple
Enter product price: 2.5
Enter product quantity: 100
```

**Making a Purchase:**
```
Enter customer number: 9876543210
Enter your name: John
Enter your email: john@gmail.com
Enter product ID: 101
Enter quantity: 5
```

**Generated Bill:**
```
Customer Name: John
Customer Number: 9876543210
Customer Email: john@gmail.com

Items Bought:
Product: Apple, Quantity: 5, Cost: $12.50

TOTAL BILL: $12.50
```

## Security Note

**Important**: This code contains hardcoded database credentials. For production use:
- Store credentials in environment variables
- Use configuration files with restricted permissions
- Never commit credentials to version control
- Implement proper user authentication

## Future Enhancements

- User authentication for owner/customer roles
- Sales history and analytics
- Product categories and search functionality
- Payment gateway integration
- Export bills to PDF
- Low stock alerts
- Multi-store support

## License

This project is open source and available under the MIT License.

## Author

Yatharth Agrawal

---

Built for efficient grocery store management with Python and MySQL

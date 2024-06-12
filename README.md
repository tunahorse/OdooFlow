# OdooFlow

OdooFlow is a Python package to create records in Odoo in a cleaner and simpler way. 

Currently, you can use OdooFlow to create sales orders in Odoo with multiple products for a specified customer identified by ID or name. The advantage being you don't have to worry about building out your own custom pipeline for the tuples, just pass the customer name and product info. 

## Installation

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install OdooFlow.

```bash
pip install OdooFlow

```

```bash
Create a .env with your login info for Odoo. Note: ENV can sometimes pickup the username from the server env so I used USERNAME_odoo. I have an example file here called .exampleenv

```
```bash
from OdooFlow import create_sales_order

customer_identifier = 'John Doe'  # Could also be an integer ID
product_ids = [30, 42]  # Product IDs
quantities = [5, 2]  # Corresponding quantities

result = create_sales_order(customer_identifier, product_ids, quantities)
print(result)
```

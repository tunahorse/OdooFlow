# OdooFlow

OdooFlow is a Python package to create records in Odoo in a cleaner and simpler way. 

Currently, you can use OdooFlow to create sales orders in Odoo with multiple products for a specified customer identified by ID or name. The advantage being you don't have to worry about building out your own custom pipeline for the tuples, just pass the customer name and product info. 

## Installation

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install OdooFlow.

```bash
pip install OdooFlow
```

After installing the package, you need to configure the environment variables.

1. Copy the `.envexample` file to create your own `.env` file:

   ```bash
   sh cp .envexample .env
   ```

2. Or you can load your own env file locally. 
  



Set up the .env with your login info for Odoo. Note: ENV can sometimes pick up the username from the server env so I used USERNAME_odoo. I have an example file here called .exampleenv, modify as needed. 

```
```bash
from OdooFlow import create_sales_order

customer_identifier = 'John Doe'  # Could also be an integer ID
product_ids = [30, 42]  # Product IDs
quantities = [5, 2]  # Corresponding quantities

result = create_sales_order(customer_identifier, product_ids, quantities)
print(result)
```

```bash
## Env Notes
If you don't change the env file from the example you can load it locally

from OdooFlow import create_sales_order

from dotenv import load_dotenv, find_dotenv
import os

# Load environment variables from .env file
load_dotenv(find_dotenv())


customer_identifier = 'John Doe'  # Could also be an integer ID
product_ids = [30, 42]  # Product IDs
quantities = [5, 2]  # Corresponding quantities

result = create_sales_order(customer_identifier, product_ids, quantities)
print(result)
```


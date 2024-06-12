
# OdooFlow

OdooFlow is a Python package designed to create records in Odoo more cleanly and simply. Currently, you can use OdooFlow to create sales orders in Odoo with multiple products for a specified customer identified by ID or name. This eliminates the need to build a custom pipeline for the tuples; simply pass the customer name and product information.

## Installation

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install OdooFlow.

\`\`\`bash
pip install OdooFlow
\`\`\`

After installing the package, you need to configure the environment variables.

1. Copy the `.envexample` file to create your own `.env` file:

    \`\`\`bash
    cp .envexample .env
    \`\`\`

2. Or you can load your own `.env` file locally.

Set up the `.env` with your login information for Odoo. Note: ENV can sometimes pick up the username from the server environment, so the username variable is `USERNAME_odoo`. Modify the `.envexample` file as needed.

### Example .env File

\`\`\`env
URL=https://your-odoo-url
DB_NAME=your_database_name
USERNAME_odoo=your_username
PASSWORD=your_password

# Add any new variables here
NEW_VARIABLE=new_value
\`\`\`

## Usage

After setting up the `.env` file, you can use the package as follows:

\`\`\`python
from OdooFlow import create_sales_order

customer_identifier = 'John Doe'  # Could also be an integer ID
product_ids = [30, 42]  # Product IDs
quantities = [5, 2]  # Corresponding quantities

result = create_sales_order(customer_identifier, product_ids, quantities)
print(result)
\`\`\`

## Environment Notes

If you don't change the environment file from the example, you can load it locally as shown below:

\`\`\`python
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
\`\`\`
"""

# Save the content to a README.md file
with open('/mnt/data/README.md', 'w') as file:
    file.write(readme_content)

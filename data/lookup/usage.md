# Usage Instructions: fica_compliance.db

### 1. Basic Connection & Query (Python)
Use Python's built-in `sqlite3` library to interact with the FICA compliance database:

```python
import sqlite3

# Connect to the database
conn = sqlite3.connect('fica_compliance.db')
cursor = conn.cursor()

# Example: Check if a user is on the Sanctions List (Scenario 3)
id_to_check = '6001138299086'
cursor.execute("SELECT * FROM sanctions_list WHERE id_number = ?", (id_to_check,))
result = cursor.fetchone()

if result:
    print(f"MATCH FOUND: {result[1]} | Risk: {result[3]} | Reason: {result[4]}")

conn.close()
```

### 2. Table Schemas
| Table | Key Columns | Purpose |
| :--- | :--- | :--- |
| **`sanctions_list`** | `full_name`, `id_number`, `risk_level`, `reason` | AML/Sanctions screening. |
| **`pep_registry`** | `full_name`, `id_number`, `position`, `is_active` | PEP (Politically Exposed Person) checks. |
| **`bank_reference`**| `bank_name`, `branch_code` | Validation of SA banking details. |

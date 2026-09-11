[README_SESSION_18.md](https://github.com/user-attachments/files/32091843/README_SESSION_18.md)
# SESSION 18

## Example 1

```python
import re

text = """
Call me at 9876543210.
Another number is 8123456789.
Price is 9999.
This is not valid: 6123456789.
WhatsApp: 7654321098
"""

pattern = r'\b[789]\d{9}\b'

numbers = re.findall(pattern, text)

print(numbers)
```

### Output

```text
['9876543210', '8123456789', '7654321098']
```

## Example 2

```python
import re

def check_date(text):
    pattern = r'\b\d{2}/\d{2}/\d{4}\b'

    if re.search(pattern, text):
        return True
    else:
        return False


print(check_date("My birthday is 25/06/2024"))
print(check_date("Today is a good day"))
```

### Output

```text
True
False
```

## Example 3

```python
import re

text = """
Zomato review:
Contact restaurant@example.com
or support@zomato.com.
My email is user123@gmail.com.
Invalid email: abc@.
"""

pattern = r'\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Za-z]{2,}\b'

emails = re.findall(pattern, text)

print(emails)
```

### Output

```text
['restaurant@example.com', 'support@zomato.com', 'user123@gmail.com']
```

## Example 4

```python
import re

text = "My phone number is 9876543210"

masked = re.sub(r'\d{6}(\d{4})', r'******\1', text)

print(masked)
```

### Output

```text
My phone number is ******3210
```

## Example 5

```python
import re

pattern = r'\bOD\d{18}\b'

orders = [
    "OD123456789012345000",
    "OD987654321098765432",
    "ABC123456789",
    "OD12345"
]

for order in orders:
    if re.search(pattern, order):
        print(order, "→ Valid Order ID")
    else:
        print(order, "→ Invalid Order ID")
```

### Output

```text
OD123456789012345000 → Valid Order ID
OD987654321098765432 → Valid Order ID
ABC123456789 → Invalid Order ID
OD12345 → Invalid Order ID
```

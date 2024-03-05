```python
#!/usr/bin/python3

# Generates a 15-character strong password with at least 3 symbols, 3 numbers, and 1 uppercase letter
# Utilizes Python secrets module as opposed to the random module for secure cryptography

import string
import secrets
character_list = string.ascii_letters + string.digits + string.punctuation
while True:
    password = ''.join(secrets.choice(character_list) for i in range(15))
    if (any(c.islower() for c in password)
            and any(c.isupper() for c in password)
            and sum(c.isdigit() for c in password) >= 3
    		and sum(c in string.punctuation for c in password) >= 3):
    	break
print(password)
```

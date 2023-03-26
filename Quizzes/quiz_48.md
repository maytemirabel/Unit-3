# Quiz 48
## Code
Use the database bitcoin_exchange.db: and create a program that check the hash signature stored for every transaction and prints:
**Tx(id=1) Signature matches or Tx(id=1) Error signature**

```.py
import sqlite3
from secure_password import check_password

class database_worker:
    def __init__(self, name):
        self.connection = sqlite3.connect(name)
        self.cursor = self.connection.cursor()

    def search(self, query):
        result = self.cursor.execute(query).fetchall()
        return result

    def run_save(self, query):
        self.cursor.execute(query)
        self.connection.commit()

    def close(self):
        self.connection.close()

x = database_worker("bitcoin_exchange.db")

query = "SELECT * from ledger"
result = x.search(query)
green = "\033[0;32m"
red = "\33[0;31m"
end_code = "\033[00m"

for row in result:
    unhashed = f"id {row[0]}, sender_id {row[1]}, receiver_id {row[2]}, amount {row[3]}"
    hashed = row[4]
    equal = check_password(hashed_pswd=hashed, user_pswd=unhashed)

    if equal:
        message = f"{green}Tx({row[0]}) Signature Matches{end_code}"
    else:
        message = f"{red}Tx({row[0]}) Error Signature{end_code}"
    print(message)
```

## Evidence of code
<img width="1021" alt="Screen Shot 2023-03-27 at 6 42 37" src="https://user-images.githubusercontent.com/105724334/227806538-f92e18dc-2e6b-4ecc-8132-5d9d92b7c772.png">

#### Figure 1: Screenshot displaying the test outcome

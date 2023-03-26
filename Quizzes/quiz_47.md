# Quiz 47
## Code
Use the Handout for Quiz 047, and the starting files quiz047.py quiz047.kv, payments.db: to create the compensation calculator
```.py
import sqlite3
from kivymd.app import MDApp
from secure_password import encrypt_password

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

class quiz047(MDApp):
    def __init__(self, **kwargs):
        super().__init__(**kwargs)
        self.components = {"basic": 0}

    def build(self):
        return

    def save(self):
        base_widget = self.root.ids.base
        base = base_widget.text.strip()
        values = {
            "base": self.root.ids.base_label.text.strip()[:-4],
            "inhabitant": self.root.ids.inhabitant_label.text.strip()[:-4],
            "income_tax": self.root.ids.income_tax_label.text.strip()[:-4],
            "pension": self.root.ids.pension_label.text.strip()[:-4],
            "health": self.root.ids.health_label.text.strip()[:-4],
            "salary": self.root.ids.salary_label.text.strip()[:-4],
            "hash": self.hash,
        }

        query = "INSERT INTO payments (base, inhabitant, income_tax, pension, health, total, hash) VALUES (?, ?, ?, ?, ?, ?, ?)"
        db = database_worker("payments.db")
        try:
            db.cursor.execute(query, [values[key] for key in values.keys()])
            db.connection.commit()
            self.root.ids.hash_label.text = "Payment saved"
        except Exception as e:
            print(f"Error saving payment: {e}")
        finally:
            db.close()
        self.root.ids.hash.text = f"Payment saved"

    def update(self):
        base = self.root.ids.base.text
        hash = ""
        test_field_ids = ['health', 'pension', 'income_tax', 'inhabitant']
        if base != "":
            total = int(base)
            hash += f"base{total}"

            for i in test_field_ids:
                value = self.root.ids[i].text
                if value != "":
                    new_value = f"{int(value) * int(base) / 100} JPY"
                    total -= int(value) * int(base) / 100
                    hash += f"{i}{value}"
                else:
                    new_value = "JPY"
                label_id = f"{i}_label"
                self.root.ids[label_id].text = new_value

            hash += f"total{int(total)}"
            self.root.ids.salary_label.text = f"{total} JPY"
            hashed = encrypt_password(hash)
            self.hash = hashed
            self.root.ids.hash.text = hashed[-50:]

    def clear(self):
        for label in ["base", "inhabitant","income_tax","pension","health"]:
            self.root.ids[label].text = ""
            self.root.ids[label+"_label"].text = " JPY"

        self.root.ids["salary_label"].text = " JPY"
        self.root.ids.hash.text = "----"

test = quiz047()
create = """CREATE TABLE if not exists payments(
     id         INTEGER primary key,
     base       INTEGER,
     inhabitant INTEGER,
     income_tax INTEGER,
     pension    INTEGER,
     health     INTEGER,
     total      INTEGER,
     hash       TEXT);"""
db = database_worker("payments.db")
db.run_save(create)
db.close()
test.run()
```

## Evidence of code
<img width="793" alt="Screen Shot 2023-03-27 at 6 56 27" src="https://user-images.githubusercontent.com/105724334/227807132-f47e3947-5ee9-47a1-8b12-8f38db7a93dc.png">

#### Figure 1: Screenshot displaying the test outcome

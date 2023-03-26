# Quiz 46
## Code
A company requires a program that calculates the average word length from a database of words. Complete the code.
```.py
import sqlite3
haiku = """Code flows like a stream
Algorithms guide its way
In silence, it solves"""
connection = sqlite3.connect("quiz46.db")
cursor = connection.cursor()

query = f"""CREATE TABLE if not exists WORDS(
        id integer primary key autoincrement,
        length integer not null,
        word text not null 
    )"""
cursor.execute(query)

for word in haiku.split():
    query2 = f"insert into WORDS(word, length) VALUES ('{word}',{len(word)})"
    cursor.execute(query2)
    connection.commit()

avg = cursor.execute("SELECT avg(length) from WORDS").fetchone()
connection.commit()
print("Average word length:", avg)
connection.close()
```

## Evidence of code
<img width="1061" alt="Screen Shot 2023-03-27 at 7 03 38" src="https://user-images.githubusercontent.com/105724334/227807500-03219c4b-7904-4370-8094-dd9f20a6d1f5.png">

#### Figure 1: Screenshot displaying the test outcome

# simulasi-livecode-3

## Step 1

### A. Buat table "book" dengan attribut "isbn" sebagai primary key :

- isbn INT AUTO_INCREMENT NOT NULL
- title VARCHAR (100)
- author VARCHAR (100)
- publisher VARCHAR (100)
- year_of_publication DATETIME

### B. Buat table "members" dengan attribut member_id sebagai primary key :

- member_id INT AUTO_INCREMENT NOT NULL
- first_name VARCHAR (100)
- last_name VARCHAR (100)
- date_of_birth DATETIME
- address VARCHAR (255)

### C. Buat table landing "transaction" dengan attribut transaction_id sebagai primary key :

- transaction_id INT AUTO_INCREMENT NOT NULL
- member_id INT
- isbn INT
- date_of_lending TIMESTAMP
- date_of_return TIMESTAMP
- condition_at_return VARCHAR 50

### Relasi Table

- Satu member (member_id) dapat memiliki beberapa transaction
- Satu buku (isbn) dapat berelasi dengan beberapa transaction
- Setiap transaksi berelasi dengan satu member dan satu buku
- Setiap transaksi yang dilakukan member dalam satu waktu tidak dapat meminjam lebih dari 5 buku

## Step 2 - Membuat ERD

<img src="https://github.com/osvaldosilitonga/simulasi-livecode-3/blob/main/ERD.jpg" />

## Step 3 - Membuat SQL Query
### Create Database "library"
```sql
CREATE DATABASE library;
```

### Switch to database
```sql
USE library;
```

### Create Table "book"
```sql
CREATE TABLE IF NOT EXISTS book(
  isbn INT AUTO_INCREMENT NOT NULL,
  author VARCHAR(100) NOT NULL,
  publisher VARCHAR(100),
  year_of_publication TIMESTAMP,
  PRIMARY KEY (isbn)
);
```

### Create Table "members"
```sql
CREATE TABLE IF NOT EXISTS members(
  member_id INT AUTO_INCREMENT NOT NULL,
  first_name VARCHAR(100) NOT NULL,
  Last_name VARCHAR(100),
  date_of_birth DATETIME,
  address VARCHAR(255),
  PRIMARY KEY (member_id)
);
```

### Create Table "transaction"
```sql
CREATE TABLE IF NOT EXISTS transaction(
  transaction_id INT AUTO_INCREMENT NOT NULL,
  member_id INT,
  isbn INT,
  date_of_lending TIMESTAMP,
  date_of_return TIMESTAMP,
  PRIMARY KEY (transaction_id),
  FOREIGN KEY (member_id) REFERENCES members(member_id),
  FOREIGN KEY (isbn) REFERENCES book(isbn)
);
```

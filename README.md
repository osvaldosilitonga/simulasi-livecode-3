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

- Buat relasi antara "member_id" sebagai foreign key - reference ke members(member_id)
- Buat relasi antara "isbn" sebagai foreign key - reference ke book(isbn)

### Relasi Table

- Satu member (member_id) dapat memiliki beberapa transaction
- Satu buku (isbn) dapat berelasi dengan beberapa transaction
- Setiap transaksi berelasi dengan satu member dan satu buku
- Setiap transaksi yang dilakukan member dalam satu waktu tidak dapat meminjam lebih dari 5 buku

## Step 2 - Membuat ERD

<img src="https://github.com/osvaldosilitonga/simulasi-livecode-3/blob/main/ERD.jpg" />

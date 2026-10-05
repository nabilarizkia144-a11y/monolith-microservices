# Praktikum Monolith dan Microservices

## Langkah-Langkah

### 1. Install Library

Buka CMD/Terminal, lalu jalankan:

```bash
pip install flask requests
```

### 2. Jalankan Monolith

```bash
python monolith/monolith_app.py
```

Server berjalan pada:

```text
http://localhost:5000
```

### 3. Tes Monolith di Postman

GET:

```text
http://localhost:5000/books
```

POST:

```text
http://localhost:5000/orders
```

Body:

```json
{
    "book_id": 1
}
```

### 4. Jalankan Book Service

Buka terminal baru:

```bash
python microservices/book_service.py
```

Server berjalan pada:

```text
http://localhost:5001
```

### 5. Tes Book Service

Di Postman:

```text
GET http://localhost:5001/books
```

### 6. Jalankan Order Service

Buka terminal baru:

```bash
python microservices/order_service.py
```

Server berjalan pada:

```text
http://localhost:5002
```

### 7. Tes Order Service

Di Postman:

```text
POST http://localhost:5002/orders
```

Body:

```json
{
    "book_id": 1
}
```

### 8. Pengujian Komunikasi

Matikan **Book Service** dengan:

```text
CTRL + C
```

Kemudian kirim kembali:

```text
POST http://localhost:5002/orders
```

Hasil:

```json
{
    "error": "Book Service sedang down!"
}
```

# Tugas 2 - Pemrograman Web Lanjutan

## Implementasi REST API menggunakan FastAPI, SQLAlchemy, dan SQLite

### Deskripsi Project

Project ini merupakan pembuatan **REST API sederhana menggunakan FastAPI** sebagai bagian dari Tugas 2 pada mata kuliah **Pemrograman Web Lanjutan**.

Aplikasi ini memanfaatkan **SQLite** sebagai sistem database dan **SQLAlchemy** sebagai ORM (Object Relational Mapping) untuk mempermudah pengelolaan data pada database. Selain itu, **Pydantic** digunakan untuk melakukan validasi data agar format data yang dikirimkan oleh API tetap terstruktur dan konsisten.

Pada project ini, API yang dibuat berfungsi untuk **mengambil data item dari database melalui endpoint tertentu**.

---

## Tujuan Pembuatan Project

Pengerjaan project ini bertujuan untuk:

* Mempelajari konsep dasar **RESTful API**
* Menggunakan **FastAPI** sebagai framework backend
* Mengimplementasikan **SQLAlchemy ORM** untuk pengelolaan database
* Menggunakan **SQLite** sebagai database lokal
* Memahami penggunaan **Pydantic** dalam validasi data
* Membuat dan menguji **endpoint API sederhana**

---

## Teknologi yang Digunakan

| Teknologi  | Kegunaan                                         |
| ---------- | ------------------------------------------------ |
| Python     | Bahasa pemrograman utama                         |
| FastAPI    | Framework untuk membangun REST API               |
| SQLAlchemy | ORM untuk menghubungkan aplikasi dengan database |
| SQLite     | Database ringan berbasis file                    |
| Pydantic   | Validasi dan pengolahan data                     |
| Uvicorn    | Server untuk menjalankan aplikasi FastAPI        |

---

## Struktur Project

Project ini disusun menggunakan struktur modular agar lebih mudah dipahami dan dikembangkan.

```
TUGAS-2-PEMROGRAMAN-WEB-LANJUTAN
│
├── main.py
├── database.py
├── models.py
├── schemas.py
├── items.db
├── requirements.txt
└── README.md
```

---

## Penjelasan Setiap File

| File             | Deskripsi                                                                 |
| ---------------- | ------------------------------------------------------------------------- |
| main.py          | File utama untuk menjalankan aplikasi FastAPI dan mendefinisikan endpoint |
| database.py      | Berisi konfigurasi koneksi database SQLite                                |
| models.py        | Mendefinisikan model tabel database menggunakan SQLAlchemy                |
| schemas.py       | Mendefinisikan schema data menggunakan Pydantic                           |
| items.db         | File database SQLite                                                      |
| requirements.txt | Berisi daftar library yang digunakan dalam project                        |

---

## Cara Menjalankan Aplikasi

### 1. Clone Repository

```
git clone https://github.com/doraemonn24/TUGAS-2-PEMROGRAMAN-WEB-LANJUTAN.git
```

### 2. Masuk ke Folder Project

```
cd TUGAS-2-PEMROGRAMAN-WEB-LANJUTAN
```

### 3. Install Dependencies

```
pip install -r requirements.txt
```

### 4. Jalankan Server

```
python -m uvicorn main:app --reload
```

Setelah server berjalan, aplikasi dapat diakses melalui:

```
http://127.0.0.1:8000
```

---

## Dokumentasi API

FastAPI menyediakan dokumentasi API secara otomatis yang bisa diakses melalui browser.

**Swagger UI**

```
http://127.0.0.1:8000/docs
```

**ReDoc**

```
http://127.0.0.1:8000/redoc
```

---

## Endpoint API

Berikut beberapa endpoint yang tersedia pada aplikasi ini:

| Method | Endpoint    | Keterangan                         |
| ------ | ----------- | ---------------------------------- |
| GET    | /items/     | Mengambil seluruh data item        |
| GET    | /items/{id} | Mengambil data item berdasarkan ID |

---

## Contoh Response API

### GET /items/

```
[
  {
    "id": 1,
    "name": "Laptop",
    "description": "Laptop untuk bekerja"
  },
  {
    "id": 2,
    "name": "Mouse",
    "description": "Mouse wireless"
  }
]
```

### GET /items/{id}

```
{
  "id": 1,
  "name": "Laptop",
  "description": "Laptop untuk bekerja"
}
```

---

## Validasi Data dengan Pydantic

Validasi data pada API dilakukan menggunakan **Pydantic Schema** yang terdapat pada file:

```
schemas.py
```

Schema ini berfungsi untuk memastikan bahwa data yang diproses oleh API memiliki struktur yang benar sebelum dikirimkan kepada client.

---

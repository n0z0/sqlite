# sqlite

```sql
-- 1. Buat tabel users
CREATE TABLE users (
    id           INTEGER PRIMARY KEY AUTOINCREMENT,
    username     TEXT NOT NULL UNIQUE,
    password     TEXT NOT NULL,
    role         TEXT NOT NULL DEFAULT 'user',
    display_name TEXT
);

-- 2. Contoh insert user admin (password masih plain, silakan ganti md5/hashed di aplikasi)
INSERT INTO users (username, password, role, display_name)
VALUES ('admin', 'admin123', 'admin', 'Administrator');

-- 3. Select semua user
SELECT * FROM users;

-- 4. Update user
UPDATE users
SET password = 'passbaru',
    role = 'user',
    display_name = 'Nama Baru'
WHERE id = 1;

-- 5. Hapus user
DELETE FROM users
WHERE id = 2;

-- 6. Cari user by username
SELECT * FROM users WHERE username = 'admin';
```

pakainya `md5($password)`, isi md5 juga di sini

```sql
UPDATE users
SET password = '21232f297a57a5a743894a0e4a801fc3' -- md5('admin')
WHERE username = 'admin';
```

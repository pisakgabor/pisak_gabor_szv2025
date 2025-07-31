# pisak_gabor_szv2025
# Szervíztámogató Rendszer – Webalkalmazás

Ez az alkalmazás lehetővé teszi ügyfelek számára, hogy műszaki termékeket adjanak le javításra online felületen keresztül. A szervíz pedig kezeli a leadott termékeket. 

## 🛠️ Technológiák
- PHP 8.1
- MySQL
- HTML5, CSS3 (Bootstrap 5)
- JavaScript (AJAX)
- Font Awesome
- google fonts
- https://unpkg.com/boxicons@2.1.4/css/boxicons.min.css

## 📦 Telepítés

1. Dumpold az adtbázist:
```sql
CREATE DATABASE IF NOT EXISTS pisak_gabor_szv2025
    DEFAULT CHARACTER SET utf8mb4
    COLLATE utf8mb4_hungarian_ci;


USE pisak_gabor_szv2025;

CREATE TABLE termekek (
    id INT AUTO_INCREMENT PRIMARY KEY,
    szeriaszam VARCHAR(100) NOT NULL,
    gyarto VARCHAR(100) NOT NULL,
    tipus VARCHAR(100) NOT NULL,
    leadas_datum DATE NOT NULL,
    statusz ENUM('Beérkezett', 'Hibafeltárás', 'Alkatrész beszerzés alatt', 'Javítás', 'Kész') NOT NULL DEFAULT 'Beérkezett',
    statusz_valtozas DATETIME NOT NULL
);

CREATE TABLE kapcsolattartok (
    id INT AUTO_INCREMENT PRIMARY KEY,
    termek_id INT NOT NULL,
    nev VARCHAR(100) NOT NULL,
    telefon VARCHAR(30) NOT NULL,
    email VARCHAR(100) NOT NULL,
    FOREIGN KEY (termek_id) REFERENCES termekek(id) ON DELETE CASCADE
);

```
2. Hozd létre az adatbázis felhasználót: 
(root, '')

3. Állítsd be a `modell/Database.php` fájlt:

```php
('localhost', 'root', '', 'pisak_gabor_szv2025')
```

4. Futtasd az alkalmazást a böngészőben:
```
https://localhost/pisak_gabor_SZV2025
```
5. Futtasd az Login-t a böngészőben:
```
https://localhost/pisak_gabor_SZV2025/login.php
```

## 👤 Alapértelmezett belépési adatok
users.php

- **Szrevizes:** szervizes / szerviz01234

## 📞 Kapcsolat
Pisák Gábor – pisakgabor@gmail.com


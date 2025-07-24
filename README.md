# 💻 StatusSyncApp – Flutter PHP MySQL Device Controller

This is a simple mobile + web-based project that allows you to **view** and **update** the status of a device using a Flutter app connected to a PHP + MySQL backend. The device's status can be toggled between `0` and `1` (e.g., OFF/ON) and is stored in a MySQL database.

---

## 🎯 Project Goal  
Learn how to:
- Build a basic Flutter mobile app that fetches and sends data over HTTP  
- Create backend APIs using PHP to interact with a MySQL database  
- Use GET requests to change values in a remote database  
- Host and test APIs on a local server (XAMPP)  
- Handle simple frontend-backend communication

---

## 🧱 What We Did

We created:
- A **Flutter app** with buttons to read and change a status value.
- A **PHP API** with two endpoints:
  - `get_run_pose.php` → fetches current device status.
  - `update_status.php` → updates the device status (0 or 1).
- A **MySQL database** (`run_db`) with a table `device_status` to store the current status.

We used **XAMPP** to host the backend locally and test API connections from the emulator.

---

## 📦 Files Included

- `lib/main.dart` → Main Flutter app file  
- `api/get_run_pose.php` → PHP script to retrieve status  
- `api/update_status.php` → PHP script to update status  
- `api/run_db.sql` → SQL file to create and seed the database  
- `README.md` → This documentation

---

## 🛠️ Tools & Technologies  
- 🧠 Flutter (mobile frontend)  
- 🖥️ PHP (backend logic)  
- 🗃️ MySQL (database)  
- 🧰 XAMPP (Apache + MySQL)  
- 🧑‍💻 Visual Studio Code  
- 📱 Android Emulator / Real Device

---

## 🧪 How It Works

1. Flutter app sends a GET request to `get_run_pose.php`
2. The script queries the `device_status` table and returns the current status
3. App shows the status on screen (0 or 1)
4. User clicks a button to toggle the status (e.g., SET STATUS TO 1)
5. Flutter app sends a GET request to `update_status.php?status=1`
6. PHP updates the value in the database accordingly

---

## 🗃️ Database Schema (run_db.sql)

```sql
CREATE DATABASE run_db;
USE run_db;

CREATE TABLE device_status (
  id INT PRIMARY KEY AUTO_INCREMENT,
  status INT NOT NULL
);

INSERT INTO device_status (status) VALUES (0);
```
---

## 🚀 How to Run the Project Locally

### 🧩 Backend (PHP + MySQL):
1. Install XAMPP
2. Start Apache and MySQL
3. Open phpMyAdmin
4. Create a new database: > run_db
5. Import > run_db.sql
6. Copy the > api/ folder into:
`C:\xampp\htdocs\StatusSyncApp\api\`
7. Visit:
`http://localhost/StatusSyncApp/api/get_run_pose.php`
`http://localhost/StatusSyncApp/api/update_status.php?status=1`

### 📱 Flutter App
1. Open project in VSCode
2. Run:
```bash
flutter pub get
flutter run
```
3. Make sure you're using 10.0.2.2 as the IP address in Flutter for `localhost` (Android emulator only)

---

## 📸 Project Preview

---

## 👤 Author
> Designed by: [Abdulrahman Qutah]  
> Date: [24 Jul 2025]

<div align="center">

# 🏨 Hotel Management Automation System

A modern system to manage hotel staff operations, room tracking, announcements, and daily meal menus —- built with **C#** and **SQL Server**, featuring **SHA256 secured authentication**.

---

### 🔧 Tech Stack

![C#](https://img.shields.io/badge/C%23-512BD4?style=for-the-badge&logo=csharp&logoColor=white)
![.NET](https://img.shields.io/badge/.NET-5C2D91?style=for-the-badge&logo=dotnet&logoColor=white)
![SQL Server](https://img.shields.io/badge/SQL%20Server-CC2927?style=for-the-badge&logo=microsoftsqlserver&logoColor=white)
![SMTP](https://img.shields.io/badge/Email%20SMTP-0078D4?style=for-the-badge&logo=microsoftoutlook&logoColor=white)

---

</div>

## ✨ Features

| Feature                         | Description                                                    |
| ------------------------------- | -------------------------------------------------------------- |
| 👥 Staff Login System           | Secure access for hotel personnel.                             |
| 🔐 SHA256 Password Hashing      | Passwords are stored securely using cryptographic hashing.     |
| 🏘️ Room Management              | Track room availability and assign customers.                  |
| 📢 Announcement Panel           | Administrators can publish important notices.                  |
| 🍽️ Daily Meal Menu              | Easily manage daily meal / cafeteria menus.                    |
| ✉️ Email-Based Account Creation | Sends verification / welcome emails to newly registered staff. |
| 🗄️ SQL Server Database          | Centralized and structured data storage.                       |

---

## 🛠️ Architecture Overview

---

## 🔐 Password Security

Passwords are **not stored as plain text**.  
Each password is hashed before being saved:

```csharp
using System.Security.Cryptography;
using System.Text;

public string HashPassword(string password)
{
    using (SHA256 sha256 = SHA256.Create())
    {
        byte[] bytes = Encoding.UTF8.GetBytes(password);
        byte[] hash = sha256.ComputeHash(bytes);
        return BitConverter.ToString(hash).Replace("-", "").ToLower();
    }
}
```
